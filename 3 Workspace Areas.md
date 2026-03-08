These are outside of the .theme-light and .theme-dark brackets.
## 3.01 Change the Tab Header Container Based on Theme Setting
```
.theme-light .workspace-tab-header-container {
	background-color: #hex ~or~ var();
}

.theme-dark .workspace-tab-header-container {
	background-color: #hex ~or~ var();
}
```
***
## 3.02 Common `mod-` Classes Explained
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
## 3.02-01 Workspace Tab Headers
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
## 3.02-02 Workspace Leaves Content Areas
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
## 3.02-03 Sidebars & Ribbons
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
## 3.02-04 Resize Handles (Between Panes)
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
## 3.02-05 Headings and their Dividers Appearance
```
/* Headings */

/* This changes them all, or you can do various ones individual */

.markdown-preview-view h1,
.markdown-preview-view h2,
.markdown-preview-view h3,
.markdown-preview-view h4,
.markdown-preview-view h5,
.markdown-preview-view h6 {
  color: var(--h1-color);
  font-weight: 600;
}


/* Dividers for Headings */

.heading-divider h1,
.heading-divider h2,
.heading-divider h3,
.heading-divider h4,
.heading-divider h5,
.heading-divider h6 {
  border-bottom: 2px solid var(--h1-color);
  padding-bottom: 4px;
}
```
## 3.02-06 Status Bar
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
## 3.02-07 Title Bar (Desktop App Only)
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
## 3.02-08 Stacked Tabs Layout
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
## 3.02-09 Workspace Drop Target (Drag & Drop)
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
## 3.02-10 Practical Examples
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
# 3.03 Some Example Settings
* Command Palette, Daily Notes, Starred Notes, Random Notes, Sync Status, Tag Pane.
```
/* Command Palette */
.suggestion-item.is-selected {
  background: rgba(64, 171, 217, 0.2);
  color: var(--text-normal);
}

/* Daily Notes */
.workspace-leaf-content[data-type="daily-notes"] .nav-file-title {
  color: var(--mushroom-accent);
}

/* Starred Notes */
.workspace-leaf-content[data-type="starred"] .nav-file-title {
  color: var(--mushroom-highlight);
}

/* Random Note */
.workspace-leaf-content[data-type="random-note"] button {
  background: var(--mushroom-accent);
  color: white;
}

/* Sync Status */
.sync-status-icon {
  color: var(--mushroom-accent);
}

/* Tag Pane */
.workspace-leaf-content[data-type="tag"] .tree-item-self {
  color: var(--tag-color);
}
```
***
# 3.04 Useful CSS Selectors Compilations
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
## 3.04-01 Accent Presets
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
## 3.04-02 Translucent Modals
*adds color to the left side of the settings window*
(This is a snippet from my Mocha Latte Cafe 002 code, change the names and colors to match your theme)
```
/* Dark Mode */
body.mocha-translucent-modals.theme-dark .modal,
body.mocha-translucent-modals.theme-dark .prompt,
body.mocha-translucent-modals.theme-dark .menu {
  background-color: rgba(30, 20, 15, 0.92) ;
  backdrop-filter: blur(10px) ;
  border: 1px solid var(--background-modifier-border) ;
  color: var(--text-normal) ;
}

/* Light Mode - Lighter, more readable */
body.mocha-translucent-modals.theme-light .modal,
body.mocha-translucent-modals.theme-light .prompt,
body.mocha-translucent-modals.theme-light .menu {
  background-color: rgba(221, 204, 188, 0.884) ; /* Light cream */
  backdrop-filter: blur(8px) ;
  border: 1px solid var(--background-modifier-border) ;
  color: var(--text-normal) ;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08) ;
}
```
add this to Styles Settings:
```
-
    id: mocha-translucent-modals
    title: Translucent Modals
    description: Semi-transparent settings windows
    type: class-toggle
    default: false
```
***
# 3.05 Style Settings Integrations
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
## 3.05-01 Add This To Styles Setting For Scrollbar Customization
```
	- id: scrollbar-header
	  title: 📜 Scrollbar
	  type: heading
	  level: 2
	  collapsed: true
	- id: scrollbar-thumb
	  title: Scrollbar Thumb Color
	  type: variable-themed-color
	  format: hex
	  default-light: '#5e489c'
	  default-dark: '#40abd9'
	- id: scrollbar-width
	  title: Scrollbar Width
	  type: variable-number-slider
	  format: px
	  default: 10
	  min: 6
	  max: 16
	  step: 1
```
## 3.05-02 Example From [Purple Mushroom Fantasy](https://github.com/breakthebull/pmf)
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
***
