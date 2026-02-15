# Theme Color Guide

## Beginning The Code - Basically

```
/* ========================================

OBSIDIAN THEME: Purple Mushroom Fantasy

AUTHOR: DA Rasmussen

LICENSE: CC0-1.0

VERSION: 1.0.1

======================================== */

/* -

GLOBAL RESETS & FOUNDATIONS

- */

  

*,

*::before,

*::after {

    box-sizing: border-box;

}

  

:root {

   /* Font Stack */
    --default-font: "Inter", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
    --font-monospace: "Source Code Pro", "Fira Code", Consolas, monospace;

   /* Typography from Style Settings */
    --font-size-normal: 16px;
    --font-size-code: 15px;
    --line-height-normal: 1.5;

}
```

---

## Additional Roots

### Typography and Font Variables

```
:root {
    /* Font Sizes */
    --font-ui-smallest: 10px;
    --font-ui-small: 12px;
    --font-ui-medium: 14px;
    --font-ui-large: 16px;
    --font-ui-largest: 18px;
    
    /* Font Weights */
    --font-normal: 400;
    --font-medium: 500;
    --font-semibold: 600;
    --font-bold: 700;
    
    /* Line Heights */
    --line-height-tight: 1.2;
    --line-height-normal: 1.5;
    --line-height-loose: 1.8;
    
    /* Letter Spacing */
    --letter-spacing-normal: 0;
    --letter-spacing-wide: 0.05em;
}
```

### Borders and Radiuses

```
:root {
    /* Border Widths */
    --border-width: 1px;
    --border-width-thin: 0.5px;
    --border-width-thick: 2px;
    
    /* Border Styles */
    --border-style-solid: solid;
    --border-style-dashed: dashed;
    --border-style-dotted: dotted;
    
    /* Border Toggle */
    --border-toggle-enabled: 1px;  /* Default: borders ON */
    --border-toggle-disabled: 0px; /* Borders OFF */
    (will add this toggle in settings)
    
    /* Border Radius */
    --radius-s: 4px;
    --radius-m: 8px;
    --radius-l: 12px;
    --radius-xl: 16px;
    --radius-full: 9999px;
}
```

### Shadows and Elevations

```
:root {
    /* Box Shadows */
    --shadow-s: 0 1px 2px rgba(0, 0, 0, 0.05);
    --shadow-m: 0 4px 6px rgba(0, 0, 0, 0.1);
    --shadow-l: 0 10px 15px rgba(0, 0, 0, 0.15);
    --shadow-xl: 0 20px 25px rgba(0, 0, 0, 0.2);
    
    /* Inset Shadows */
    --shadow-inset: inset 0 1px 2px rgba(0, 0, 0, 0.05);
}
```

### Gradients

```
:root {
    /* Linear Gradients */
    --gradient-primary: linear-gradient(135deg, var(--color001), var(--color002));
    --gradient-secondary: linear-gradient(135deg, var(--color003), var(--color004));
    --gradient-tertiary: linear-gradient(135deg, var(--color005), var(--color006));
    
    /* Radial Gradients */
    --gradient-radial: radial-gradient(circle, var(--color001), var(--color002));
}
```

### Transitions and Animations

```
:root {
    /* Transition Durations */
    --transition-fast: 0.1s;
    --transition-normal: 0.2s;
    --transition-slow: 0.3s;
    
    /* Transition Timing Functions */
    --transition-ease: ease;
    --transition-ease-in: ease-in;
    --transition-ease-out: ease-out;
    --transition-ease-in-out: ease-in-out;
    --transition-linear: linear;
}
```

### Mobile Responsive

```
:root {
    /* Breakpoints */
    --breakpoint-mobile: 480px;
    --breakpoint-tablet: 768px;
    --breakpoint-desktop: 1024px;
    
    /* Mobile-specific */
    --mobile-font-size: 14px;
    --mobile-padding: 16px;
}
```

---

## Next, Light or Dark?

```
.theme-light {
	(color designs for light theme will go in here)
}

.theme-dark {
	(color designs for dark theme will go in here)
}
```

---

## Pick A Palette, and Stick to it

```
.theme-light {
	--color001: #hex;
	--color002: #hex;
	--color003: #hex;
	--color004: #hex;
	--color005: #hex;
	--color007: #hex;
}
```

**add more, or use less. color001-7 can be changed to whatever you want, and add '-dark' to the dark palette color names under .theme-dark or just keep numbering in a sequence that is not the exact same name as the ones under .theme-light**

While still within these parameters of either .theme-light or .theme-dark, use the following;

### Backgrounds

```
	--background-primary: #hex ~or~ var();
	--background-primary-alt: #hex ~or~ var();
	--background-secondary: #hex ~or~ var();
	--background-secondary-alt: #hex ~or~ var();
```

### Modifiers

```
	--background-modifier-border: #hex ~or~ var();
	--background-modifier-form-field: #hex ~or~ var();
	--background-modifier-form-field-highlighted: #hex ~or~ var();
	--background-modifier-hover: #hex ~or~ var();
	--background-modifier-border-hover: #hex ~or~ var();
	--background-modifier-border-focus: #hex ~or~ var();
```

### Text

```
	--text-active: #hex ~or~ var();
	--text-muted: #hex ~or~ var();
	--text-faint: #hex ~or~ var();
	--text-accent: #hex ~or~ var();
	--text-on-accent: #hex ~or~ var();
	--text-accent-hover: #hex ~or~ var();
	--text-on-accent-hover: #hex ~or~ var();
```

### Interactive

```
	--interactive-accent: #hex ~or~ var();
	--interactive-accent-hover: #hex ~or~ var();
	--interactive-normal: #hex ~or~ var();
	--interactive-hover: #hex ~or~ var();
```

### Tags

```
	--tag-background: #hex ~or~ var();
	--tag-color: #hex ~or~ var();
	--tag-background-hover: #hex ~or~ var();
	--tag-color-hover: #hex ~or~ var();
	--tag-border-color: #hex ~or~ var();
```

### Metadata

```
	--metadata-label-text-color: #hex ~or~ var();
	--metadata-label-background: #hex ~or~ var();
	--metadata-property-background: #hex ~or~ var();
```

### Buttons

```
	--button-background: #hex ~or~ var();
	--button-color: #hex ~or~ var();
	--button-background-hover: #hex ~or~ var();
	--button-color-hover: #hex ~or~ var();
```

### Highlights

```
	--text-highlight-bg: #hex ~or~ var();
	--text-selection: #hex ~or~ var();
```

### Links

```
	--link-color: #hex ~or~ var();
	--link-color-hover: #hex ~or~ var();
	--backlink-border-color: #hex ~or~ var();
    --backlink-background: #hex ~or~ var();
    --backlink-title-color: #hex ~or~ var();
```

### Headings

```
	--h1-color: #hex ~or~ var();
	--h2-color: #hex ~or~ var();
	--h3-color: #hex ~or~ var();
	--h4-color: #hex ~or~ var();
	--h5-color: #hex ~or~ var();
	--h6-color: #hex ~or~ var();
```

### Checkboxes

```
	--checkbox-color: #hex ~or~ var();
	--checkbox-color-hover: #hex ~or~ var();
```

### Scrollbar

```
	--scrollbar-thumb-bg: #hex ~or~ var();
	--scrollbar-active-thumb-bg: #hex ~or~ var();
	--scrollbar-background: #hex ~or~ var();
	--scrollbar-color: #hex ~or~ var();
```

### Code Blocks

```
	--code-background: #hex ~or~ var();
	--code-normal: #hex ~or~ var();
	--code-comment: #hex ~or~ var();
	--code-function: #hex ~or~ var();
	--code-keyword: #hex ~or~ var();
	--code-string: #hex ~or~ var();
	--code-number: #hex ~or~ var();
```

### Icons

```
	--icon-color-normal: #hex ~or~ var();
	--icon-color-hover: #hex ~or~ var();
	--icon-color: #hex ~or~ var();
```

### Nav Items

```
	--nav-item-color: #hex ~or~ var();
	--nav-item-color-hover: #hex ~or~ var();
	--nav-item-color-active: #hex ~or~ var();
	--nav-item-background-hover: #hex ~or~ var();
	--nav-item-background-active: #hex ~or~ var();
```

### Titlebar

```
	--titlebar-background-color: #hex ~or~ var();
	--titlebar-color: #hex ~or~ var();
```

### Block Quotes

```
	--blockquote-border-color: #hex ~or~ var();
```

### Callouts

```
	--callout-color: #hex ~or~ var();
	--callout-background: #hex ~or~ var();
```

### Status Bar

```
	--status-bar-background: #hex ~or~ var();
	--status-bar-item: #hex ~or~ var();
	--status-bar-item-hover: #hex ~or~ var();
```

### Graphs

```
	--graph-line: #hex ~or~ var();
	--graph-node: #hex ~or~ var();
	--graph-node-tag: #hex ~or~ var();
	--graph-node-focused: #hex ~or~ var();
	--graph-node-attachment: #hex ~or~ var();
	--graph-node-unresolved: #hex ~or~ var();
```

### Tables

```
	--table-border-color: #hex ~or~ var();
    --table-header-background: #hex ~or~ var();
    --table-row-even-background: #hex ~or~ var();
    --table-row-odd-background: #hex ~or~ var();
    --table-row-hover-background: #hex ~or~ var();
```

### Lists

```
	--list-marker-color: #hex ~or~ var();
    --list-indent: 2em;
    --list-spacing: 0.5em;
```

### Horizontal Rules

```
	--hr-color: #hex ~or~ var();
    --hr-thickness: 1px;
    --hr-style: solid;
```

### Sidebars and Ribbons

```
	--ribbon-background: #hex ~or~ var();
    --ribbon-background-collapsed: #hex ~or~ var();
    --sidebar-background: #hex ~or~ var();
    --sidebar-border-color: #hex ~or~ var();
```

### Models and Popovers

```
	--modal-background: #hex ~or~ var();
    --modal-border-color: #hex ~or~ var();
    --popover-background: #hex ~or~ var();
    --popover-border-color: #hex ~or~ var();
```

### Search Command Palette

```
	--search-result-background: #hex ~or~ var();
    --search-result-background-active: #hex ~or~ var();
    --search-result-border: #hex ~or~ var();
    --suggestion-background: #hex ~or~ var();
    --suggestion-background-active: #hex ~or~ var();
```

### Core Plugin Support

```
/* Kanban */
    --kanban-lane-background: #hex ~or~ var();
    --kanban-card-background: #hex ~or~ var();
    --kanban-card-border: #hex ~or~ var();

/* Dataview */
    --dataview-table-border: #hex ~or~ var();
    --dataview-header-background: #hex ~or~ var();
    
/* Calendar */
    --calendar-day-background: #hex ~or~ var();
    --calendar-day-active: #hex ~or~ var();
    --calendar-day-today: #hex ~or~ var();
    
```

---

## Border Toggle

Add this at the end of the file above Styles Settings:

```
/* Apply Border Toggle */
body.toggle-borders-off * {
    border-width: var(--border-toggle-disabled) !important;
}

/* Specific border elements to target */
body.toggle-borders-off .modal,
body.toggle-borders-off .prompt,
body.toggle-borders-off .menu,
body.toggle-borders-off .workspace-ribbon,
body.toggle-borders-off .workspace-tabs,
body.toggle-borders-off .status-bar,
body.toggle-borders-off button,
body.toggle-borders-off input,
body.toggle-borders-off textarea,
body.toggle-borders-off select,
body.toggle-borders-off .dropdown,
body.toggle-borders-off .nav-file-title,
body.toggle-borders-off .nav-folder-title,
body.toggle-borders-off .workspace-tab-header,
body.toggle-borders-off table,
body.toggle-borders-off th,
body.toggle-borders-off td,
body.toggle-borders-off blockquote,
body.toggle-borders-off pre {
    border-width: var(--border-toggle-disabled) !important;
}

/* Keep essential borders (scrollbars, etc.) */
body.toggle-borders-off ::-webkit-scrollbar-thumb {
    border: none !important;
}

```

## Workspace Areas

These are outside of the .theme-light and .theme-dark brackets.

### Change the Tab Header Container Based on Theme Setting

```
.theme-light .workspace-tab-header-container {
	background-color: #hex ~or~ var();
}

.theme-dark .workspace-tab-header-container {
	background-color: #hex ~or~ var();
}
```

---

## Common `mod-` Classes Explained

```css
/* Left Sidebar (File Explorer, etc.) */
.mod-left-split {
    /* Applied to left sidebar panels */
}

/* Right Sidebar (Backlinks, Outline, etc.) */
.mod-right-split {
    /* Applied to right sidebar panels */
}

/* Top Workspace Area (Main content area) */
.mod-top {
    /* Applied to the main workspace tabs area */
}

/* Vertical Split (Side-by-side panes) */
.mod-vertical {
    /* Applied when panes are split vertically */
}

/* Horizontal Split (Stacked panes) */
.mod-horizontal {
    /* Applied when panes are split horizontally */
}

/* Root Workspace (Main container) */
.mod-root {
    /* Applied to the root workspace container */
}

/* Active Tab */
.mod-active {
    /* Applied to the currently active tab */
}

/* Stacked Tabs (Side tabs instead of top) */
.mod-stacked {
    /* Applied when tabs are stacked on the side */
}

/* Mobile View */
.is-mobile {
    /* Applied on mobile devices */
}

/* Fullscreen Mode */
.is-fullscreen {
    /* Applied when in fullscreen mode */
}
```

### Workspace Tab Headers

```css
/* All Tab Headers Container */
.workspace-tab-header-container {
    background-color: var(--background-secondary);
    border-bottom: 1px solid var(--background-modifier-border);
}

/* Individual Tab Header */
.workspace-tab-header {
    color: var(--text-muted);
    background-color: transparent;
}

/* Active Tab */
.workspace-tab-header.is-active {
    color: var(--text-accent);
    background-color: var(--background-primary);
    border-bottom: 3px solid var(--interactive-accent);
}

/* Hover State */
.workspace-tab-header:hover {
    background-color: var(--background-modifier-hover);
    color: var(--text-normal);
}

/* Tab Close Button */
.workspace-tab-header-inner-close-button {
    color: var(--text-faint);
}

.workspace-tab-header-inner-close-button:hover {
    color: var(--text-error);
    background-color: var(--background-modifier-hover);
}

/* New Tab Button (+) */
.workspace-tab-header-new-tab {
    color: var(--text-muted);
}

.workspace-tab-header-new-tab:hover {
    color: var(--text-accent);
    background-color: var(--background-modifier-hover);
}

/* Tab Menu Button (⋮) */
.workspace-tab-header-tab-list {
    color: var(--text-muted);
}

.workspace-tab-header-tab-list:hover {
    color: var(--text-normal);
    background-color: var(--background-modifier-hover);
}
```

### Workspace Leaves Content Areas

```css
/* Main Content Area */
.workspace-leaf {
    background-color: var(--background-primary);
}

/* Leaf Content (The actual view) */
.workspace-leaf-content {
    background-color: var(--background-primary);
}

/* View Header (Title bar of each pane) */
.view-header {
    background-color: var(--background-secondary);
    border-bottom: 1px solid var(--background-modifier-border);
    color: var(--text-normal);
}

/* View Header Title */
.view-header-title {
    color: var(--text-normal);
    font-weight: 600;
}

/* View Content Area */
.view-content {
    background-color: var(--background-primary);
}
```

### Sidebars & Ribbons

```css
/* Left Ribbon (Sidebar toggle icons) */
.workspace-ribbon.mod-left {
    background-color: var(--background-secondary);
    border-right: 1px solid var(--background-modifier-border);
}

/* Right Ribbon */
.workspace-ribbon.mod-right {
    background-color: var(--background-secondary);
    border-left: 1px solid var(--background-modifier-border);
}

/* Ribbon Icons */
.workspace-ribbon .clickable-icon {
    color: var(--icon-color);
}

.workspace-ribbon .clickable-icon:hover {
    color: var(--icon-color-hover);
    background-color: var(--background-modifier-hover);
}

/* Sidebar Toggle Button */
.sidebar-toggle-button {
    background-color: var(--background-secondary);
    color: var(--text-muted);
}

.sidebar-toggle-button:hover {
    background-color: var(--background-modifier-hover);
    color: var(--text-normal);
}

/* Sidebar Pin Button */
.workspace-ribbon-pin-btn {
    color: var(--text-muted);
}

.workspace-ribbon-pin-btn:hover {
    color: var(--text-accent);
}
```

### Resize Handles (Between Panes)

```css
/* Vertical Split Handle (Between side-by-side panes) */
.workspace-split.mod-vertical > .workspace-leaf-resize-handle {
    background-color: var(--background-modifier-border);
    width: 3px;
}

.workspace-split.mod-vertical > .workspace-leaf-resize-handle:hover {
    background-color: var(--interactive-accent);
    width: 5px;
}

/* Horizontal Split Handle (Between stacked panes) */
.workspace-split.mod-horizontal > .workspace-leaf-resize-handle {
    background-color: var(--background-modifier-border);
    height: 3px;
}

.workspace-split.mod-horizontal > .workspace-leaf-resize-handle:hover {
    background-color: var(--interactive-accent);
    height: 5px;
}
```

### Status Bar

```css
/* Status Bar Container */
.status-bar {
    background-color: var(--status-bar-background, var(--background-secondary));
    border-top: 1px solid var(--background-modifier-border);
    color: var(--text-muted);
}

/* Status Bar Items */
.status-bar-item {
    color: var(--text-muted);
}

.status-bar-item:hover {
    color: var(--text-normal);
    background-color: var(--background-modifier-hover);
}

/* Clickable Status Bar Items */
.status-bar-item.mod-clickable:hover {
    color: var(--text-accent);
    cursor: pointer;
}
```

### Title Bar (Desktop App Only)

```css
/* Title Bar Container */
.titlebar {
    background-color: var(--titlebar-background, var(--background-secondary));
    border-bottom: 1px solid var(--background-modifier-border);
    color: var(--titlebar-color, var(--text-normal));
}

/* Title Bar Buttons (Minimize, Maximize, Close) */
.titlebar-button {
    color: var(--text-muted);
}

.titlebar-button:hover {
    background-color: var(--background-modifier-hover);
}

/* Mac Window Controls */
.is-mac .titlebar-inner {
    padding-left: 70px; /* Space for traffic lights */
}
```

### Stacked Tabs Layout

```css
/* Stacked Tab Container */
.workspace-tabs.mod-stacked {
    /* Tabs appear on the side instead of top */
}

/* Stacked Tab Headers */
.workspace-tabs.mod-stacked .workspace-tab-header-container {
    width: var(--tab-stacked-header-width, 40px);
    background-color: var(--background-secondary);
}

/* Stacked Tab Header (Vertical) */
.workspace-tabs.mod-stacked .workspace-tab-header {
    height: auto;
    padding: 8px 0;
    text-align: center;
}

/* Active Stacked Tab */
.workspace-tabs.mod-stacked .workspace-tab-header.is-active {
    background-color: var(--background-primary);
    border-right: 3px solid var(--interactive-accent);
    border-bottom: none;
}
```

### Workspace Drop Target (Drag & Drop)

```css
/* Drop Overlay (When dragging files/panes) */
.workspace-drop-overlay {
    background-color: rgba(0, 0, 0, 0.1);
    border: 2px dashed var(--interactive-accent);
}

/* Drop Target Indicator */
.workspace-drop-indicator {
    background-color: var(--interactive-accent);
}
```

### Practical Examples

```css
/* Make active tab header match accent color */
.workspace-tab-header.is-active {
    background: linear-gradient(135deg, var(--interactive-accent), var(--text-accent));
    color: var(--text-on-accent);
    border-bottom: 3px solid var(--interactive-accent);
}

/* Rounded corners on workspace leaves */
.workspace-leaf {
    border-radius: var(--radius-m);
    overflow: hidden;
}

/* Gradient title bar */
.titlebar {
    background: linear-gradient(135deg, var(--background-secondary), var(--interactive-accent));
    color: white;
}

/* Hide status bar */
.status-bar {
    display: none;
}

/* Make sidebar icons glow on hover */
.workspace-ribbon .clickable-icon:hover {
    color: var(--interactive-accent);
    text-shadow: 0 0 8px rgba(var(--interactive-accent-rgb), 0.5);
}

/* Different background for left vs right sidebar */
.mod-left-split .workspace-leaf-content {
    background-color: rgba(var(--background-primary-rgb), 0.98);
}

.mod-right-split .workspace-leaf-content {
    background-color: rgba(var(--background-primary-rgb), 0.95);
}

/* Highlight active pane with border */
.mod-active .workspace-leaf {
    border: 2px solid var(--interactive-accent);
}

/* Make resize handles more visible */
.workspace-leaf-resize-handle:hover {
    background-color: var(--interactive-accent);
    transition: all 0.2s ease;
}
```

---

## Useful CSS Selectors Compilations

```
/* Active file in file explorer */
.nav-file-title.is-active,
.nav-folder-title.is-active {
    /* styles */
}

/* Hover states */
.nav-file-title:hover,
.nav-folder-title:hover {
    /* styles */
}

/* Workspace tabs */
.workspace-tab-header.is-active {
    /* styles */
}

/* Status bar items */
.status-bar-item.mod-clickable:hover {
    /* styles */
}

/* Code blocks */
.markdown-preview-view pre,
.markdown-source-view pre {
    /* styles */
}

/* Blockquotes */
.markdown-preview-view blockquote {
    /* styles */
}

/* Callouts */
.callout {
    /* styles */
}

/* Task list items */
.task-list-item-checkbox {
    /* styles */
}

/* Internal links */
.cm-hmd-internal-link,
.internal-link {
    /* styles */
}

/* External links */
.external-link {
    /* styles */
}

/* Unresolved links */
.cm-hmd-internal-link.is-unresolved,
.internal-link.is-unresolved {
    /* styles */
}
```

### Accent Presets

Essentially recoloring your established color names. Changes the elements those colors are being used by. Can use all in your palette or just do a few. Can make MANY different accents.

```
/* Default Accent */
body.accent-default {
  --color001: #40abd9;
  --color002: #6bc8ff;
  --color003: #5140b0;
  (add more here)
}

/* Purple Glow Accent */
body.accent-purple {
  --color001: #9d6bff;
  --color002: #c49dff;
  --color003: #7a42ff;
  (add more here)
}
```

Then, add to your Styles Settings area in your CSS. Here you can name them whatever you want. Be sure to create a label for each preset you have.

```
-
    id: accent-presets-header
    title: 🎨 Accent Presets
    type: heading
    level: 1
    collapsed: false
  -
    id: accent-preset
    title: Quick Accent Preset
    description: Instantly change the theme's mood
    type: class-select
    allowEmpty: true
    default: accent-purple
    options:
      -
        label: '🔵 Default Blue'
        value: 'accent-default'
      -
        label: '💜 Purple Glow'
        value: 'accent-purple'
```

---

## Style Settings Integrations

```
/* ========================================
STYLE SETTINGS INTEGRATION
======================================== */
/* Add this comment block at the end of your theme */
/* @settings
name: Your Theme Name
id: your-theme-id
settings:
    - id: section-header-1
      title: Colors
      type: heading
      level: 1
      collapsed: false
      
    - id: primary-accent
      title: Primary Accent
      type: variable-themed-color
      format: hex
      default-light: '#hex'
      default-dark: '#hex'
      
    - id: text-normal
      title: Normal Text
      type: variable-themed-color
      format: hex
      default-light: '#hex'
      default-dark: '#hex'
      
    - id: border-radius
      title: Border Radius
      type: variable-number-slider
      format: px
      default: 8
      min: 0
      max: 16
      step: 1
*/
```


### Example From [Purple Mushroom Fantasy](https://github.com/breakthebull/pmf)

```
/* ========================================
STYLE SETTINGS CONFIGURATION
======================================== */
/* @settings

name: 🍄 Purple Mushroom Fantasy
id: purple-mushroom-fantasy
settings:
  -
    id: accent-presets-header
    title: 🎨 Accent Presets
    type: heading
    level: 1
    collapsed: false
  -
    id: accent-preset
    title: Quick Accent Preset
    description: Instantly change the theme's mood
    type: class-select
    allowEmpty: true
    default: accent-purple
    options:
      -
        label: 'None (Custom)'
        value: 'none'
      -
        label: '🔵 Default Blue'
        value: 'accent-default'
      -
        label: '💜 Purple Glow'
        value: 'accent-purple'
      -
        label: '💚 Emerald Green'
        value: 'accent-emerald'
      -
        label: '🧡 Amber Glow'
        value: 'accent-amber'
      -
        label: '🩷 Rose Pink'
        value: 'accent-rose'
      -
        label: '🔴 Crimson Red'
        value: 'accent-crimson'
  -
    id: base-colors-header
    title: 🎭 Base Colors
    type: heading
    level: 1
    collapsed: true
  -
    id: mushroom-base
    title: Base Background
    type: variable-themed-color
    format: hex
    default-light: '#f8fafc'
    default-dark: '#0d1524'
  -
    id: mushroom-secondary
    title: Secondary Background
    type: variable-themed-color
    format: hex
    default-light: '#e2e8f0'
    default-dark: '#240f3f'
  -
    id: mushroom-accent
    title: Primary Accent
    type: variable-themed-color
    format: hex
    default-light: '#5e489c'
    default-dark: '#40abd9'
  -
    id: mushroom-highlight
    title: Secondary Accent
    type: variable-themed-color
    format: hex
    default-light: '#5893b1'
    default-dark: '#5140b0'
  -
    id: text-header
    title: 📝 Text Colors
    type: heading
    level: 2
    collapsed: true
  -
    id: text-normal
    title: Normal Text
    type: variable-themed-color
    format: hex
    default-light: '#1e293b'
    default-dark: '#e0e6ff'
  -
    id: text-muted
    title: Muted Text
    type: variable-themed-color
    format: hex
    default-light: '#64748b'
    default-dark: '#a0b0d0'
  -
    id: text-accent
    title: Accent Text (Links)
    type: variable-themed-color
    format: hex
    default-light: '#5e489c'
    default-dark: '#40abd9'
  -
    id: interface-header
    title: 🖥️ Interface
    type: heading
    level: 2
    collapsed: true
  -
    id: border-radius
    title: Border Radius
    type: variable-number-slider
    format: px
    default: 6
    min: 0
    max: 16
    step: 1
  -
    id: glow-effect
    title: Enable Glow Effects
    type: class-toggle
    default: true
  -
    id: typography-header
    title: 🔤 Typography
    type: heading
    level: 1
    collapsed: true
  -
    id: font-size-normal
    title: Base Font Size
    description: Main text size (Ctrl+Scroll still works)
    type: variable-number-slider
    default: 16
    min: 12
    max: 24
    step: 0.5
    format: px
  -
    id: font-size-code
    title: Code Font Size
    type: variable-number-slider
    default: 15
    min: 10
    max: 20
    step: 0.5
    format: px
  -
    id: line-height
    title: Line Height
    type: variable-number-slider
    default: 1.6
    min: 1.2
    max: 2.0
    step: 0.1
  -
    id: headings-header
    title: 📋 Headings
    type: heading
    level: 2
    collapsed: true
  -
    id: colorful-headings
    title: Colorful Headings
    type: class-toggle
    default: false
  -
    id: h1-color
    title: H1 Color
    type: variable-themed-color
    format: hex
    default-light: '#5e489c'
    default-dark: '#5140b0'
  -
    id: h2-color
    title: H2 Color
    type: variable-themed-color
    format: hex
    default-light: '#5893b1'
    default-dark: '#40abd9'
  -
    id: heading-divider
    title: Heading Divider Lines
    type: class-toggle
    default: true
  -
    id: links-header
    title: 🔗 Links
    type: heading
    level: 2
    collapsed: true
  -
    id: link-underline
    title: Link Underlines
    type: class-toggle
    default: false
  -
    id: link-underline-hover
    title: Underline on Hover
    type: class-toggle
    default: true
  -
    id: link-unresolved-opacity
    title: Unresolved Link Opacity
    type: variable-number-slider
    default: 0.7
    min: 0.2
    max: 1.0
    step: 0.1
  -
    id: tags-header
    title: 🏷️ Tags
    type: heading
    level: 2
    collapsed: true
  -
    id: tag-shape
    title: Tag Shape
    type: variable-select
    default: '14px'
    options:
      -
        label: 'Pill'
        value: '14px'
      -
        label: 'Rounded'
        value: '4px'
      -
        label: 'Square'
        value: '0px'
  -
    id: tag-border-width
    title: Tag Border Width
    type: variable-select
    default: '1px'
    options:
      -
        label: 'None'
        value: '0px'
      -
        label: 'Thin'
        value: '1px'
      -
        label: 'Thick'
        value: '2px'
  -
    id: plugin-header
    title: 🔌 Plugin Support
    type: heading
    level: 1
    collapsed: true
  -
    id: graph-colors-header
    title: Graph View
    type: heading
    level: 3
    collapsed: true
  -
    id: graph-line
    title: Graph Line Color
    type: variable-themed-color
    format: hex
    default-light: '#5e489c'
    default-dark: '#2560a0'
  -
    id: graph-node
    title: Graph Node Color
    type: variable-themed-color
    format: hex
    default-light: '#5893b1'
    default-dark: '#40abd9'
  -
    id: graph-node-tag
    title: Tag Node Color
    type: variable-themed-color
    format: hex
    default-light: '#804c3e'
    default-dark: '#5140b0'
  -
    id: calendar-header
    title: Calendar
    type: heading
    level: 3
    collapsed: true
  -
    id: calendar-accent
    title: Calendar Accent
    type: variable-themed-color
    format: hex
    default-light: '#5893b1'
    default-dark: '#5140b0'
  -
    id: misc-header
    title: 🎛️ Miscellaneous
    type: heading
    level: 2
    collapsed: true
  -
    id: status-bar-off
    title: Hide Status Bar
    type: class-toggle
    default: false
  -
    id: ribbon-off
    title: Hide Ribbon
    type: class-toggle
    default: false
*/
```