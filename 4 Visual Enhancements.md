Here are beginner-friendly CSS snippets you can drop into your **CSS Snippets folder** (`Settings → Appearance → CSS snippets`). Each is self-contained and works immediately when toggled on!
# 4.01 **Colored Blockquotes**
Makes blockquotes stand out with a colored border.
```css
/* Colored blockquotes with left border */
blockquote {
  border-left: 4px solid var(--interactive-accent) !important;
  background-color: var(--background-secondary) !important;
  padding: 1em !important;
  border-radius: 0 4px 4px 0 !important;
}
```
***
# 4.02 **Rounded Corners Everywhere**
Softens the entire UI with rounded elements.
```css
/* Rounded corners for cards, modals, and more */
.theme-dark .modal,
.theme-light .modal,
.workspace-leaf,
.workspace-tab-header-container,
.workspace-tab-header-inner-icon,
.workspace-leaf-content,
.view-content,
.markdown-preview-view,
.markdown-source-view,
.workspace-split.mod-vertical > * {
  border-radius: 8px !important;
}

/* Also round modals and popovers */
.popover,
.prompt,
.suggestion-container {
  border-radius: 8px !important;
}
```
***
# 4.03 **Custom Scrollbar**
Makes scrollbars prettier and thinner.
```css
/* Custom scrollbar styling */
::-webkit-scrollbar {
  width: 8px !important;
  height: 8px !important;
}

::-webkit-scrollbar-track {
  background: transparent !important;
}

::-webkit-scrollbar-thumb {
  background: var(--scrollbar-thumb-bg) !important;
  border-radius: 4px !important;
}

::-webkit-scrollbar-thumb:hover {
  background: var(--scrollbar-active-thumb-bg) !important;
}
```
***
# 4.04 Editor & Reading Improvements
## 4.04-01 **Wider Editor (More Writing Space)**
Increases the max width of the editor and preview.
```css
/* Wider editor and preview pane */
.markdown-source-view.mod-cm6 .cm-content,
.markdown-preview-view {
  max-width: 900px !important;
  margin-left: auto !important;
  margin-right: auto !important;
}

/* Also widen modals like "Insert Link" */
.modal.mod-community-theme,
.modal {
  max-width: 800px !important;
}
```
## 4.04-02 **Line Numbers in Editor**
Shows line numbers when editing (CodeMirror 6).
```css
/* Show line numbers in editor */
.cm-gutters {
  display: flex !important;
  border-right: 1px solid var(--background-modifier-border) !important;
}

.cm-gutterElement {
  color: var(--text-muted) !important;
}
```
## 4.04-03 **Focus Mode (Dim Other Lines)**
Highlights the current line you're typing on.
```css
/* Highlight current line in editor */
.cm-active {
  background-color: var(--background-secondary) !important;
}

/* Dim inactive lines slightly */
.cm-line:not(.cm-active) {
  opacity: 0.8 !important;
}
```
***
# 4.05 Tag & Link Styling
## 4.05-01 **Pretty Tags**
Makes tags look like colorful badges.
```css
/* Pretty tag styling */
a.tag {
  background-color: var(--interactive-accent) !important;
  color: white !important;
  padding: 0.2em 0.6em !important;
  border-radius: 12px !important;
  font-size: 0.9em !important;
  text-decoration: none !important;
  border: none !important;
  box-shadow: 0 1px 2px rgba(0,0,0,0.1) !important;
}

a.tag:hover {
  opacity: 0.9 !important;
  transform: scale(1.05) !important;
  transition: all 0.2s ease !important;
}
```
## 4.05-02 **Underline Internal Links**
Makes internal links more visible.
```css
/* Underline internal links only */
.internal-link {
  text-decoration: underline !important;
  text-decoration-color: var(--interactive-accent) !important;
  text-decoration-thickness: 2px !important;
  text-underline-offset: 2px !important;
}

.internal-link:hover {
  text-decoration-thickness: 3px !important;
}
```
***
# 4.06 Status Bar & Interface
## 4.06-01 **Hide Status Bar**
Cleans up the bottom of the screen.
```css
/* Hide status bar completely */
.status-bar {
  display: none !important;
}
```
## 4.06-02 **Semi-Transparent Sidebars**
Makes sidebars slightly see-through.
```css
/* Transparent sidebars */
.workspace-tabs,
.workspace-ribbon {
  background-color: rgba(0, 0, 0, 0.7) !important;
}

.theme-light .workspace-tabs,
.theme-light .workspace-ribbon {
  background-color: rgba(255, 255, 255, 0.85) !important;
}

/* Optional: blur effect */
.workspace-tabs,
.workspace-ribbon {
  backdrop-filter: blur(10px) !important;
  -webkit-backdrop-filter: blur(10px) !important;
}
```
***
# 4.07 Callouts & Highlights
## 4.07-01 **Highlight Search Results**
Makes searched text more prominent.
```css
/* Highlight search results in editor */
.cm-searchMatch {
  background-color: rgba(255, 215, 0, 0.3) !important;
  outline: 2px solid rgba(255, 215, 0, 0.6) !important;
}

/* Highlight search results in preview */
.markdown-preview-view mark {
  background-color: rgba(255, 215, 0, 0.4) !important;
  padding: 0.1em 0.2em !important;
  border-radius: 2px !important;
}
```
## 4.07-02 **Custom Highlight Color**
Changes the default yellow highlight to something prettier.
```css
/* Custom highlight color (when you use ==text==) */
mark {
  background-color: rgba(74, 144, 226, 0.3) !important;
  color: var(--text-normal) !important;
  padding: 0.1em 0.2em !important;
  border-radius: 2px !important;
}
```
***
# 4.08 Task & List Tweaks
## 4.08-01 **Bigger Checkboxes**
Makes task checkboxes easier to click.
```css
/* Larger checkboxes for tasks */
.markdown-preview-view .task-list-item-checkbox,
.markdown-source-view .task-list-item-checkbox {
  transform: scale(1.3) !important;
  margin-right: 0.5em !important;
}

/* Style checked items */
.markdown-preview-view .task-list-item-checkbox:checked {
  background-color: var(--interactive-accent) !important;
  border-color: var(--interactive-accent) !important;
}
```
## 4.08-02 **Bullet Point Colors**
Adds color to unordered list bullets.
```css
/* Colored bullet points */
ul > li::marker {
  color: var(--interactive-accent) !important;
  font-weight: bold !important;
}
```
***
# 4.09 Minimal Mode Helpers
## 4.09-01 **Hide Title Bar**
Removes the file title at the top of notes.
```css
/* Hide note title */
.view-header-title {
  display: none !important;
}

/* Optional: also hide the entire header */
.view-header {
  display: none !important;
}
```
## 4.09-02 **Hide Folder Pane Icons**
Cleans up the file explorer.
```css
/* Hide folder/file icons in explorer */
.nav-file-icon,
.nav-folder-icon {
  display: none !important;
}

/* Keep indentation */
.nav-file-title,
.nav-folder-title {
  padding-left: 10px !important;
}
```
***
# 4.10 Bonus: Quick Theme Switcher Helper
## 4.10-01 **Dark/Light Mode Toggle Button**
Adds a button to the status bar to switch themes.
> ⚠️ **Note**: This requires the **"Buttons" plugin** to work.
```css
/* Style for theme toggle button (works with Buttons plugin) */
.theme-toggle-btn {
  background: var(--interactive-accent) !important;
  color: white !important;
  border: none !important;
  padding: 4px 12px !important;
  border-radius: 4px !important;
  font-size: 0.9em !important;
}
```
***
