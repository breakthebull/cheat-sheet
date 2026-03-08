*A step-by-step guide for adding base64-encoded background images to sidebar panels*
***
# 2.01 Overview
This technique adds custom background images to your theme's **sidebar panels** (File Explorer, Backlinks, Tag pane, etc.) using base64 encoding. The image is embedded directly in your CSS file, making it portable and self-contained.
***
# 2.02 Step 1: Prepare Your Image
## A. Choose the Right Image
* **Format**: SVG (recommended) or PNG/JPG
* **Size**: Keep under 50KB when encoded (compress first!)
* **Style**: Subtle patterns/textures work best (avoid busy images)
## B. Compress & Optimize
* **SVG**: Use [SVGOMG](https://jakearchibald.github.io/svgomg/)
* **PNG/JPG**: Use [TinyPNG](https://tinypng.com/) or [Squoosh](https://squoosh.app/)
## C. Convert to Base64
* **Online**: [Base64 Encoder](https://www.base64-image.de/)
* **Command Line**:
  ```bash
  # For SVG
  base64 -i your-image.svg

  # For PNG
  base64 -i your-image.png
  ```
> 💡 **Pro Tip**: Remove line breaks from your base64 string – it must be a single continuous line!
***
# 2.03 Step 2: Add the Background CSS
## A. Target the Correct Elements
Add this CSS block to your theme file (place after your `:root` section):
```css
/* ========================================
   SIDEBAR BACKGROUND - Base64 Image
   ======================================== */
.mod-sidedock .workspace-leaf-content {
  background-image: url("image/svg+xml;base64,YOUR_BASE64_STRING_HERE");
  background-size: cover;        /* or 'contain', 'repeat' */
  background-position: center;   /* adjust as needed */
  background-repeat: no-repeat; /* or 'repeat' for patterns */
  background-attachment: local;  /* scrolls with content */
  position: relative;           /* required for overlay */
}
```
## B. Replace the Placeholder
* Replace `YOUR_BASE64_STRING_HERE` with your actual base64 string
* Change `image/svg+xml` to `image/png` or `image/jpeg` if using those formats
***
# 2.04 Step 3: Ensure Text Readability
## A. Add a Dark Overlay (Recommended)
This prevents washed-out text in light mode:
```css
/* Dark overlay for readability */
.mod-sidedock .workspace-leaf-content::before {
  content: "";
  position: absolute;
  inset: 0;
  background: rgba(0, 0, 0, 0.4); /* Dark mode */
  background: rgba(255, 255, 255, 0.1); /* Light mode override */
  pointer-events: none;
  z-index: 0;
}

/* Keep content above overlay */
.mod-sidedock .workspace-leaf-content > * {
  position: relative;
  z-index: 1;
}
```
## B. Adjust Overlay Darkness
* **Darker**: Increase alpha value (e.g., `0.6` instead of `0.4`)
* **Lighter**: Decrease alpha value (e.g., `0.2` instead of `0.4`)
***
# 2.05 Step 4: Make It Theme-Aware (Optional)
If you want different images for dark/light modes:
```css
/* Dark Mode Background */
.theme-dark .mod-sidedock .workspace-leaf-content {
  background-image: url("image/svg+xml;base64,YOUR_DARK_BASE64");
}

/* Light Mode Background */
.theme-light .mod-sidedock .workspace-leaf-content {
  background-image: url("image/svg+xml;base64,YOUR_LIGHT_BASE64");
}
```
> 💡 Create a darker, more saturated version of your image for light mode to prevent washout.
***
# 2.06 Step 5: Add Style Settings Toggle
## A. Add to Your `@settings` Block
Include this in your YAML configuration:
```yaml
- id: sidebar-bg-toggle
  title: Sidebar Background Image
  description: Enable base64 background in side panels
  type: class-toggle
  default: true
```
## B. Wrap CSS in Toggle Class
Modify your background CSS to only apply when enabled:
```css
/* Only show background when toggle is ON */
body.sidebar-bg-toggle .mod-sidedock .workspace-leaf-content {
  background-image: url("image/svg+xml;base64,YOUR_BASE64_STRING_HERE");
  /* ... other background properties */
}

/* Overlay only when background is active */
body.sidebar-bg-toggle .mod-sidedock .workspace-leaf-content::before {
  /* ... overlay properties */
}
```

#### Example:

```
/* ========================================
   SIDEBAR BACKGROUND - Base64 Image
   ======================================== */
.theme-dark .mod-sidedock .workspace-leaf-content {
  background-image: url("image/svg+xml;base64,YOUR_BASE64_STRING_HERE");
  background-size: cover;        /* or 'contain', 'repeat' */
  background-position: center;   /* adjust as needed */
  background-repeat: no-repeat; /* or 'repeat' for patterns */
  background-attachment: local;  /* scrolls with content */
  position: relative;           /* required for overlay */
  filter: brightness(0.9) contrast(1.0) saturate(1.3);
  background-blend-mode: multiply;
  background-color: var(--espresso-hover);
}

/* Dark overlay for readability */
.theme-dark .mod-sidedock .workspace-leaf-content::before {
  content: "";
  position: absolute;
  inset: 0;
  background: rgba(0, 0, 0, 0.4); /* Dark mode */
  pointer-events: none;
  z-index: 0;
}

.theme-dark .mod-sidedock .workspace-leaf-content {
  background-image: url("image/svg+xml;base64,YOUR_BASE64_STRING_HERE");
  background-size: cover;        /* or 'contain', 'repeat' */
  background-position: center;   /* adjust as needed */
  background-repeat: no-repeat; /* or 'repeat' for patterns */
  background-attachment: local;  /* scrolls with content */
  position: relative;           /* required for overlay */
  filter: brightness(0.9) contrast(1.0) saturate(1.3);
  background-blend-mode: multiply;
  background-color: var(--espresso-hover);
}

/* Dark overlay for readability */
.theme-light .mod-sidedock .workspace-leaf-content::before {
  content: "";
  position: absolute;
  inset: 0;
  background: rgba(0, 0, 0, 0.4); /* Dark mode */
  pointer-events: none;
  z-index: 0;
}

/* Keep content above overlay */
.mod-sidedock .workspace-leaf-content > * {
  position: relative;
  z-index: 1;
  backdrop-filter: blur(1.5px);
}

/* add this if putting in styles settings: body.sidebar-bg-toggle  */
```

***
# 2.07 Step 6: Test & Troubleshoot
## 2.07-01 Common Issues & Fixes:
| Issue                    | Solution                                                                              |
| ------------------------ | ------------------------------------------------------------------------------------- |
| **Image not showing**    | Check base64 string has no line breaks; verify data URL format                        |
| **Text unreadable**      | Add/adjust the overlay darkness; ensure `position: relative` on parent                |
| **Affects wrong panels** | Confirm you're targeting `.mod-sidedock .workspace-leaf-content`                      |
| **Performance lag**      | Compress image further; keep base64 under 50KB                                        |
| **Toggle not working**   | Verify class name matches (`sidebar-bg-toggle`) and CSS uses `body.sidebar-bg-toggle` |
## 2.07-02 Testing Checklist:
* ✅ Dark mode: Background visible, text readable
* ✅ Light mode: Background visible, text readable
* ✅ Toggle OFF: No background appears
* ✅ Toggle ON: Background appears with proper overlay
* ✅ All sidebar panels affected (File Explorer, Backlinks, Tags, etc.)
***
# 2.08 Tips
## 2.08-01 Performance Optimization
* **Use SVG** when possible (smaller file size, scales perfectly)
* **Avoid large photos** – stick to simple patterns or illustrations
* **Test file size** – themes over 100KB may slow down Obsidian
## 2.08-02 Design Best Practices
* **Subtlety is key** – backgrounds should enhance, not distract
* **Match your theme** – use colors from your existing palette
* **Consider accessibility** – ensure sufficient contrast for all users
## 2.08-03 Advanced Customization
* **Different images per panel**: Target specific data types:
  ```css
  /* File Explorer only */
  .workspace-leaf-content[data-type="file-explorer"] .workspace-leaf-content { }

  /* Tag pane only */
  .workspace-leaf-content[data-type="tag"] .workspace-leaf-content { }
  ```
***
# 2.09 Example Complete Implementation
```css
/* Style Settings Toggle */
body.sidebar-bg-toggle .mod-sidedock .workspace-leaf-content {
  background-image: url("image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTAwIiBoZWlnaHQ9IjEwMCI+PGNpcmNsZSBjeD0iNTAiIGN5PSI1MCIgcj0iNDAiIGZpbGw9InJlZCIvPjwvc3ZnPg==");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  background-attachment: local;
  position: relative;
}

/* Readability overlay */
body.sidebar-bg-toggle .mod-sidedock .workspace-leaf-content::before {
  content: "";
  position: absolute;
  inset: 0;
  background: rgba(0, 0, 0, 0.4);
  pointer-events: none;
  z-index: 0;
}

body.sidebar-bg-toggle .mod-sidedock .workspace-leaf-content > * {
  position: relative;
  z-index: 1;
}
```
With this setup, users get a beautiful, customizable background that enhances your theme without sacrificing readability! 🍄✨
