# 1.01 Theme Color Guide

## 1.02 Beginning The Code - Basically

(most examples are used by [Purple Mushroom Fantasy](https://github.com/breakthebull/pmf) and [Mocha Latte Cafe 002](https://github.com/breakthebull/cappuccino))

```
/* ========================================
OBSIDIAN THEME: Theme Name
AUTHOR: Your Name
LICENSE: CC0-1.0
VERSION: version #
======================================== */

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

## 1.03 Additional Roots

### 1.03-1 Typography and Font Variables

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

### 1.03-2 Borders and Radiuses

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

### 1.03-3 Shadows and Elevations

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

### 1.03-4 Gradients

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

### 1.03-5 Transitions and Animations

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

### 1.03-6 Mobile Responsive

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

## 1.04 Next, Light or Dark?

*If I put this (!) that means it belongs OUTSIDE the '.theme {}' area*

```
.theme-light {
	(color designs for light theme will go in here)
}

.theme-dark {
	(color designs for dark theme will go in here)
}
```

---

## 1.05 Pick A Palette, and Stick to it

```
.theme-light {
	--color001: #hex;
	--color002: #hex;
	--color003: #hex;
	--color004: #hex;
	--color005: #hex;
	--color006: #hex;
	--color007: #hex;
}
```

**add more, or use less. color001-7 can be changed to whatever you want, and add '-dark' to the dark palette color names under .theme-dark or just keep numbering in a sequence that is not the exact same name as the ones under .theme-light**

While still within these parameters of either .theme-light or .theme-dark, use the following;

### 1.05-01 Backgrounds

```
	--background-primary: #hex ~or~ var(); /*Note background*/
	--background-primary-alt: #hex ~or~ var(); /*Note Title background active*/
	--background-secondary: #hex ~or~ var(); /*Sidebar background*/
	--background-secondary-alt: #hex ~or~ var(); /*Sidebar Title background*/
```

### 1.05-02 Modifiers

```
	--background-modifier-border: #hex ~or~ var(); /*Border outline of quotes, tables, line breaks*/
	--background-modifier-form-field: #hex ~or~ var();
	--background-modifier-form-field-highlighted: #hex ~or~ var();
	--background-modifier-hover: #hex ~or~ var();
	--background-modifier-border-hover: #hex ~or~ var();
	--background-modifier-border-focus: #hex ~or~ var();
	--background-modifier-cover: #hex ~or~ var(); /*Obsidian Title Bar Bg*/

```

#### (!) Embeds use modifiers--optional

```
/* Embeds */
.markdown-embed, .file-embed {
    border: 1px solid var(--background-modifier-border);
    background-color: var(--background-primary-alt);
}
.markdown-embed-title, .file-embed-title {
    border-bottom: 1px solid var(--background-modifier-border);
    color: var(--text-active);
}
.markdown-embed-link, .file-embed-link {
    color: var(--text-accent);
}
```

#### (!) Form Elements (the search boxes)

```
/* Form Elements */
input, textarea, .dropdown {
    background-color: var(--background-modifier-form-field);
    border-color: var(--background-modifier-border);
    color: var(--text-normal);
}
input:focus, textarea:focus {
    border-color: var(--background-modifier-border-focus);
    box-shadow: 0 0 0 2px rgba(201, 140, 104, 0.28);
}
```

### 1.05-03 Text

```
	--text-normal: #hex ~or~ var(); /*Text body of note*/
	--text-muted: #hex ~or~ var(); /*Text darker for sidebar, toggles, inactive, tags, etc*/
	--text-faint: #hex ~or~ var(); /*Link brackets color & Gutter Numbers*/
	--text-accent: #hex ~or~ var(); /*Links*/
	--text-on-accent: #hex ~or~ var();
	--text-accent-hover: #hex ~or~ var(); /*Links hover*/
	--text-on-accent-hover: #hex ~or~ var();
	--text-selection: #hex ~or~ var(); /*Text Selections*/
```

#### (!) Typography Rules Example Code

```
/* Bold & Italic */
strong {
  color: var(--mushroom-highlight);
  font-weight: 600;
}

em {
  color: var(--mushroom-accent);
  font-style: italic;
}
```

### 1.05-04 Dropdowns

```
--dropdown-background: #hex ~or~ var();
```

### 1.05-05 Interactive

```
	--interactive-normal: #hex ~or~ var(); /*Button Color*/
    --interactive-hover: #hex ~or~ var(); /*Button Hovered Color*/
    --interactive-accent: #hex ~or~ var(); /*Workspace Note Title Underline*/
    --interactive-accent-hover: #hex ~or~ var(); /*Menu Button Hover*/
```

### 1.05-06 Tags

```
	--tag-background: #hex ~or~ var();
	--tag-color: #hex ~or~ var();
	--tag-background-hover: #hex ~or~ var();
	--tag-color-hover: #hex ~or~ var();
	--tag-border-color: #hex ~or~ var();
```

#### (!) Tags Example Code

```
/* Tags */
.tag {
  background: var(--tag-background);
  color: var(--tag-color);
 border: var(--tag-border-width, 1px) solid var(--tag-border-color);
  border-radius: var(--tag-shape, 14px);
  padding: 2px 8px;
  font-size: 0.85em;
  transition: all 0.2s ease;
}

.tag:hover {
  background: rgba(81, 64, 176, 0.3);
  box-shadow: 0 0 8px rgba(81, 64, 176, 0.4);
}
```

### 1.05-07 Metadata

```
	--metadata-label-text-color: #hex ~or~ var();
	--metadata-label-background: #hex ~or~ var();
	--metadata-property-background: #hex ~or~ var();
```

#### (!) Frontmatter/Properties/Metadata Example Code (Used Theme Mocha Latte Cafe 002 snippet)

```
/* Frontmatter */
.frontmatter-container,
.cm-hmd-frontmatter {
    background-color: var(--metadata-label-background);
    border-bottom: 1px dashed var(--background-modifier-border);
    color: var(--metadata-label-text-color);
}
.frontmatter-container .frontmatter-alias {
    color: var(--espresso-base);
}
```

### 1.05-08 Buttons

*(this will override the interactives if you want the buttons separate from your chosen interactive color placements)*

```
	--button-background: #hex ~or~ var();
	--button-color: #hex ~or~ var();
	--button-background-hover: #hex ~or~ var();
	--button-color-hover: #hex ~or~ var();
```

#### (!) Buttons Example Codes

```
/* Buttons */
button,
.button {
  background: var(--button-normal);
  color: var(--text-normal);
  border: 1px solid var(--mushroom-spore);
  border-radius: var(--border-radius, 6px);
  transition: all 0.2s ease;
}

button:hover,
.button:hover {
  background: var(--button-hover);
  border-color: var(--mushroom-mid);
  transform: translateY(-1px);
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

button.mod-cta,
.button.mod-cta {
  background: var(--mushroom-accent);
  color: white;
  border-color: var(--mushroom-accent);
}

button.mod-cta:hover {
  background: var(--mushroom-glow);
  border-color: var(--mushroom-glow);
}
```

### 1.05-09 Highlights

```
	--text-highlight-bg: #hex ~or~ var(); /*Search Matches*/
    --text-highlight-bg-active: #hex ~or~ var(); /*Active Search Match (Preview Mode)*/
```

### 1.05-10 Links

*(this will override the accent links if you need these to be separate from your accent chosen locations)*

```
	--link-color: #hex ~or~ var();
	--link-color-hover: #hex ~or~ var();
	--backlink-border-color: #hex ~or~ var();
    --backlink-background: #hex ~or~ var();
    --backlink-title-color: #hex ~or~ var();
```

#### (!) Links Example Code

```
/* Links */
a,
.cm-hmd-internal-link,
.cm-url,
.external-link {
  color: var(--text-accent);
  text-decoration: none;
  transition: all 0.2s ease;
}

.link-underline a,
.link-underline .cm-hmd-internal-link,
.link-underline .cm-url,
.link-underline .external-link {
  text-decoration: underline;
}

.link-underline-hover a:hover,
.link-underline-hover .cm-hmd-internal-link:hover,
.link-underline-hover .cm-url:hover,
.link-underline-hover .external-link:hover {
  text-decoration: underline;
  text-decoration-color: var(--text-accent);
}

a:hover,
.cm-hmd-internal-link:hover {
  color: var(--text-accent-hover);
}

a.is-unresolved,
.cm-hmd-internal-link.is-unresolved {
  opacity: var(--link-unresolved-opacity, 0.7);
  color: var(--mushroom-poison);
}
```

### 1.05-11 Headings

```
	--h1-color: #hex ~or~ var();
	--h2-color: #hex ~or~ var();
	--h3-color: #hex ~or~ var();
	--h4-color: #hex ~or~ var();
	--h5-color: #hex ~or~ var();
	--h6-color: #hex ~or~ var();
```

### 1.05-12 Checkboxes

```
	--checkbox-color: #hex ~or~ var();
	--checkbox-color-hover: #hex ~or~ var();
```

#### (!) Checkboxes Example Code

```
/* Checkboxes */
input[type="checkbox"] {
  accent-color: var(--mushroom-accent);
}
```

### 1.05-13 Scrollbar

```
	--scrollbar-thumb-bg: #hex ~or~ var();
	--scrollbar-active-thumb-bg: #hex ~or~ var();
	--scrollbar-background: #hex ~or~ var();
	--scrollbar-color: #hex ~or~ var();
```

#### (!) Cursor Blink Example Code -- optional

```
.cm-cursorLayer .cm-cursor {
    border-left: 1.2px solid var(--espresso-base);
    margin-left: -0.6px;
}
.cm-cursorLayer {
    animation-name: none;
}
@keyframes phase-blink {
    15% { opacity: 1; }
    50% { opacity: 0.2; }
    85% { opacity: 1; }
}
.cm-cursorLayer .cm-cursor {
    animation: phase-blink 2200ms steps(1) infinite;
}
```

### 1.05-14 Code Blocks

```
	--code-background: #hex ~or~ var();
	--code-normal: #hex ~or~ var();
	--code-comment: #hex ~or~ var();
	--code-function: #hex ~or~ var();
	--code-keyword: #hex ~or~ var();
	--code-string: #hex ~or~ var();
	--code-number: #hex ~or~ var();
```

#### (!) Code Blocks Example Code

```
/* Code Blocks */
.markdown-preview-view pre,
.markdown-source-view pre {
  background: var(--code-background);
  border-left: 4px solid var(--mushroom-accent);
  border-radius: var(--border-radius, 6px);
  padding: 12px 16px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

code {
  background: var(--code-background);
  color: var(--code-normal);
  padding: 2px 6px;
  border-radius: 3px;
}
```

### 1.05-15 Icons

```
	--icon-color-normal: #hex ~or~ var();
	--icon-color-hover: #hex ~or~ var();
	--icon-color: #hex ~or~ var();
	--search-icon-color: #hex ~or~ var();
```

### 1.05-16 Nav Items

```
	--nav-item-color: #hex ~or~ var();
	--nav-item-color-hover: #hex ~or~ var();
	--nav-item-color-active: #hex ~or~ var();
	--nav-item-background-hover: #hex ~or~ var();
	--nav-item-background-active: #hex ~or~ var();
```

#### (!) Nav File Explorer Example Code

```
.nav-file-title,
.nav-folder-title {
  color: var(--text-muted);

}

.nav-file-title:hover,
.nav-folder-title:hover {
  background: rgba(64, 171, 217, 0.1);
}

.nav-file-title.is-active,
.nav-folder-title.is-active {
  background: rgba(81, 64, 176, 0.3);
  color: var(--mushroom-glow, #6bc8ff);
  border-left: 3px solid var(--mushroom-accent, #40abd9);
}
```

#### (!) In case of transparent text in a sidebar plugin

```
.mod-split .nav-file-title-content,
.mod-split .nav-folder-title-content {
    --text-normal: var(--text-muted);
}
```

### 1.05-17 Titlebar

```
	--titlebar-background-color: #hex ~or~ var();
	--titlebar-color: #hex ~or~ var();
```

#### (!) Titlebar Example Code

```
/* Title Bar */
.titlebar-text,
.titlebar-button.mod-logo {
    color: var(--espresso-base);
    opacity: 1;
}
.titlebar-button {
    color: var(--icon-color-normal);
}
```

### 1.05-18 Block Quotes

```
	--blockquote-border-color: #hex ~or~ var();
```

#### (!) Block Quotes Example Code

```
/* Blockquotes */
.markdown-preview-view blockquote {
  border-left: 4px solid var(--blockquote-border-color);
  background: rgba(64, 171, 217, 0.08);
  color: var(--text-normal);
  padding: 8px 16px;
  margin: 16px 0;
  border-radius: 0 6px 6px 0;
}
```

### 1.05-19 Callouts

```
	--callout-color: #hex ~or~ var();
	--callout-background: #hex ~or~ var();
```

#### (!) Callouts Code Example

```
/* Callouts */
.callout {
  border-left: 4px solid var(--callout-color);
  background: var(--callout-background);
  border-radius: 0 6px 6px 0;
  padding: 12px 16px;
  margin: 16px 0;
}
```

### 1.05-20 Status Bar

```
	--status-bar-background: #hex ~or~ var();
	--status-bar-item: #hex ~or~ var();
	--status-bar-item-hover: #hex ~or~ var();
```

#### (!) Status Bar Example Code

```
/* Status Bar */
.status-bar {
  background: var(--status-bar-background, #182b59);
  border-top: 1px solid var(--mushroom-spore, #3a558c);
  color: var(--text-muted);
}

.status-bar-item:hover {
  color: var(--mushroom-accent, #40abd9);
}

.status-bar-off .status-bar {
  display: none;
}
```

### 1.05-21 Graphs

```
	--graph-line: #hex ~or~ var();
	--graph-node: #hex ~or~ var();
	--graph-node-tag: #hex ~or~ var();
	--graph-node-focused: #hex ~or~ var();
	--graph-node-attachment: #hex ~or~ var();
	--graph-node-unresolved: #hex ~or~ var();
```

#### (!) Graphs Example Code

```
/* Graph View */
.graph-view.color-fill {
  color: var(--graph-node, #40abd9);
}

.graph-view.color-fill-focused {
  color: var(--graph-node-focused, #6bc8ff);
}

.graph-view.color-fill-tag {
  color: var(--graph-node-tag, #5140b0);
}

.graph-view.color-fill-attachment {
  color: var(--graph-node-attachment, #2560a0);
}

.graph-view.color-fill-unresolved {
  color: var(--graph-node-unresolved, #ff528f);
}

.graph-view.color-line {
  color: var(--graph-line, #3a558c);
}

.graph-view.color-text {
  color: var(--text-normal);
}
```

### 1.05-22 Tables

```
	--table-border-color: #hex ~or~ var();
    --table-header-background: #hex ~or~ var();
    --table-row-even-background: #hex ~or~ var();
    --table-row-odd-background: #hex ~or~ var();
    --table-row-hover-background: #hex ~or~ var();
```

#### (!) Tables Example Code

```
/* Tables */
th {
  background: var(--table-header-background) !important;
  color: var(--mushroom-glow) !important;
  font-weight: 600;
}

tr:nth-child(even) {
  background: var(--table-row-even-background);
}

tr:nth-child(odd) {
  background: var(--table-row-odd-background);
}
```

### 1.05-23 Lists

```
	--list-marker-color: #hex ~or~ var();
    --list-indent: 2em;
    --list-spacing: 0.5em;
```

### 1.05-24 Horizontal Rules

```
	--hr-color: #hex ~or~ var();
    --hr-thickness: 1px;
    --hr-style: solid;
```

#### (!) Horizontal Rules Example Code

```
/* Horizontal Rules */
hr {
  border-color: var(--mushroom-spore);
  opacity: 0.5;
}
```

### 1.05-25 Sidebars and Ribbons

```
	--ribbon-background: #hex ~or~ var();
    --ribbon-background-collapsed: #hex ~or~ var();
    --sidebar-background: #hex ~or~ var();
    --sidebar-border-color: #hex ~or~ var();
```

#### (!) Ribbons Example Code

```
/* Ribbon */
.ribbon-off .workspace-ribbon {
  display: none;
}
```

### 1.05-26 Models and Popovers

```
	--modal-background: #hex ~or~ var();
    --modal-border-color: #hex ~or~ var();
    --popover-background: #hex ~or~ var();
    --popover-border-color: #hex ~or~ var();
```

#### (!) Hover and Popover Example Code

```
.theme-dark .popover.hover-editor {
  --he-title-bar-inactive-bg: var(--background-secondary);
  --he-title-bar-active-bg: var(--background-secondary);
  --he-title-bar-inactive-fg: var(--text-muted);
  --he-title-bar-active-fg: var(--text-normal);
}

.theme-light .popover.hover-editor {
  --he-title-bar-inactive-bg: var(--background-secondary);
  --he-title-bar-active-bg: var(--background-secondary);
  --he-title-bar-inactive-fg: var(--text-muted);
  --he-title-bar-active-fg: var(--text-normal);
}

.modal,
.prompt {
  background: var(--background-primary);
  border: 1px solid var(--mushroom-spore);
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
}
```

#### (!) Modals and Tooltip

```
.modal, .prompt, .menu, .tooltip {
    background-color: var(--background-primary);
    border-color: var(--background-modifier-border);
    color: var(--text-normal);
}
.tooltip {
    --element-selector-highlight-outline: 1px dashed var(--interactive-accent);
    --element-selector-highlight-background-color: rgba(201, 140, 104, 0.25);
    --element-selector-tooltip-background-color: var(--background-primary);
    --element-selector-tooltip-border: 1px solid var(--background-modifier-border);
    --element-selector-tooltip-border-radius: 6px;
    --element-selector-tooltip-padding: 1em;
}
```

### 1.05-27 Search Command Palette

```
	--search-result-background: #hex ~or~ var();
    --search-result-background-active: #hex ~or~ var();
    --search-result-border: #hex ~or~ var();
    --suggestion-background: #hex ~or~ var();
    --suggestion-background-active: #hex ~or~ var();
```

### 1.05-28 Core Plugin Support

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

#### (!) Core Plugin Support Example Code

```
/* Dataview */
.theme-dark .dataview.table-view-table,
.theme-dark .dataview.table-view-table th,
.theme-dark .dataview.table-view-table td {
  border-color: var(--mushroom-spore);
}

.theme-light .dataview.table-view-table,
.theme-light .dataview.table-view-table th,
.theme-light .dataview.table-view-table td {
  border-color: var(--mushroom-spore);
}

/* Kanban */
body .kanban-plugin {
  --kanban-border: var(--border-width);
  --interactive-accent: var(--kanban-accent, var(--mushroom-accent));
  --interactive-accent-hover: var(--mushroom-glow);
  background-color: var(--background-primary);
}

body .kanban-plugin__lane {
  background: var(--background-secondary);
  border-radius: var(--border-radius, 6px);
}

body .kanban-plugin__item {
  background: var(--background-primary);
  border-radius: var(--border-radius, 4px);
  border-left: 3px solid var(--kanban-accent, var(--mushroom-accent));
}

/* Calendar */
.calendar-container {
  --calendar-dot-active: var(--calendar-accent, var(--mushroom-accent));
  --calendar-dot-today: var(--mushroom-highlight);
}

.calendar-container .day.today {
  color: var(--mushroom-highlight);
  font-weight: 600;
}

.calendar-container .day.active {
  color: var(--calendar-accent, var(--mushroom-accent));
}
```

### 1.05- 29 Sync Avatar (optional if you keep track of multiple vaults)

- The avatar typically displays the first letter of your account email/name against a colored background. This variable defines that background color to help it blend with your theme's aesthetic.
- This variable is only relevant if you use Obsidian Sync. If you don't use Sync, this variable has no visible effect in your vault. Theme developers include it to ensure Sync UI elements match the overall theme design when users do enable Sync.

```
	--sync-avatar-color-current-user: #hex ~or~ var();
```

#### (!) Sync Status Icon

```
/* Sync Status */
.sync-status-icon {
  color: var(--mushroom-accent);
}
```

#### (!) Vault Name Color

```
.workspace-ribbon .workspace-ribbon-collapse-btn,
.workspace-ribbon .workspace-ribbon-pin-btn {
    color: var(--espresso-base);
}
```

---

## 1.06 Before Code, After '.theme {}' Sections

```
*,
*::before,
*::after {
  box-sizing: border-box;
}*/

/*----Startup Progress Bar Screen----*/
/*Startup Progress Bar Window*/
.progress-bar {}

/*Startup Text*/
.progress-bar .progress-bar-message {}

/*Startup Progress Bar Background*/
.progress-bar-indicator .progress-bar-line {}

/*Startup Progress Bar Moving Line*/
.progress-bar-indicator .progress-bar-subline {}
```

## 1.07 Border Toggle

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

## 1.08 Search Bar Example

```
/* Search */
.search-result {
  border-left: 3px solid var(--mushroom-accent, #40abd9);
}

.search-result.is-active {
  background: rgba(64, 171, 217, 0.15);
}
```

### 1.08-01 Notifications Example Code

```
.notice {
    background-color: var(--background-modifier-cover);
    color: var(--text-normal);
    border-left: 3px solid var(--espresso-base);
}
```

# 2.01 Base64 Background Images in Obsidian Themes  
*A step-by-step guide for adding base64-encoded background images to sidebar panels*

---

## 2.02 Overview
This technique adds custom background images to your theme's **sidebar panels** (File Explorer, Backlinks, Tag pane, etc.) using base64 encoding. The image is embedded directly in your CSS file, making it portable and self-contained.

---

## 2.03 Step 1: Prepare Your Image

### A. Choose the Right Image
- **Format**: SVG (recommended) or PNG/JPG
- **Size**: Keep under 50KB when encoded (compress first!)
- **Style**: Subtle patterns/textures work best (avoid busy images)

### B. Compress & Optimize
- **SVG**: Use [SVGOMG](https://jakearchibald.github.io/svgomg/)
- **PNG/JPG**: Use [TinyPNG](https://tinypng.com/) or [Squoosh](https://squoosh.app/)

### C. Convert to Base64
- **Online**: [Base64 Encoder](https://www.base64-image.de/)
- **Command Line**:  
  ```bash
  # For SVG
  base64 -i your-image.svg
  
  # For PNG
  base64 -i your-image.png
  ```

> 💡 **Pro Tip**: Remove line breaks from your base64 string – it must be a single continuous line!

---

## 2.04 Step 2: Add the Background CSS

### A. Target the Correct Elements
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

### B. Replace the Placeholder
- Replace `YOUR_BASE64_STRING_HERE` with your actual base64 string
- Change `image/svg+xml` to `image/png` or `image/jpeg` if using those formats

---

## 2.05 Step 3: Ensure Text Readability

### A. Add a Dark Overlay (Recommended)
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

### B. Adjust Overlay Darkness
- **Darker**: Increase alpha value (e.g., `0.6` instead of `0.4`)
- **Lighter**: Decrease alpha value (e.g., `0.2` instead of `0.4`)

---

## 2.06 Step 4: Make It Theme-Aware (Optional)

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

---

## 2.07 Step 5: Add Style Settings Toggle

### A. Add to Your `@settings` Block
Include this in your YAML configuration:

```yaml
- id: sidebar-bg-toggle
  title: Sidebar Background Image
  description: Enable base64 background in side panels
  type: class-toggle
  default: true
```

### B. Wrap CSS in Toggle Class
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

---

## 2.08 Step 6: Test & Troubleshoot

### 2.08-01 Common Issues & Fixes:

| Issue | Solution |
|-------|----------|
| **Image not showing** | Check base64 string has no line breaks; verify data URL format |
| **Text unreadable** | Add/adjust the overlay darkness; ensure `position: relative` on parent |
| **Affects wrong panels** | Confirm you're targeting `.mod-sidedock .workspace-leaf-content` |
| **Performance lag** | Compress image further; keep base64 under 50KB |
| **Toggle not working** | Verify class name matches (`sidebar-bg-toggle`) and CSS uses `body.sidebar-bg-toggle` |

### 2.08-02 Testing Checklist:
- ✅ Dark mode: Background visible, text readable
- ✅ Light mode: Background visible, text readable  
- ✅ Toggle OFF: No background appears
- ✅ Toggle ON: Background appears with proper overlay
- ✅ All sidebar panels affected (File Explorer, Backlinks, Tags, etc.)

---

## 2.09 Tips

### 2.09-01 Performance Optimization
- **Use SVG** when possible (smaller file size, scales perfectly)
- **Avoid large photos** – stick to simple patterns or illustrations
- **Test file size** – themes over 100KB may slow down Obsidian

### 2.09-02 Design Best Practices
- **Subtlety is key** – backgrounds should enhance, not distract
- **Match your theme** – use colors from your existing palette
- **Consider accessibility** – ensure sufficient contrast for all users

### 2.09-03 Advanced Customization
- **Different images per panel**: Target specific data types:
  ```css
  /* File Explorer only */
  .workspace-leaf-content[data-type="file-explorer"] .workspace-leaf-content { }
  
  /* Tag pane only */
  .workspace-leaf-content[data-type="tag"] .workspace-leaf-content { }
  ```

---

## 2.10 Example Complete Implementation

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

# 3.01 Workspace Areas

These are outside of the .theme-light and .theme-dark brackets.

### 3.02 Change the Tab Header Container Based on Theme Setting

```
.theme-light .workspace-tab-header-container {
	background-color: #hex ~or~ var();
}

.theme-dark .workspace-tab-header-container {
	background-color: #hex ~or~ var();
}
```

---

## 3.03 Common `mod-` Classes Explained

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

### 3.03-01 Workspace Tab Headers

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

### 3.03-02 Workspace Leaves Content Areas

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

### 3.03-03 Sidebars & Ribbons

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

### 3.03-04 Resize Handles (Between Panes)

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

### 3.03-05 Headings and their Dividers Appearance

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

### 3.03-06 Status Bar

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

### 3.03-07 Title Bar (Desktop App Only)

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

### 3.03-08 Stacked Tabs Layout

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

### 3.03-09 Workspace Drop Target (Drag & Drop)

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

### 3.03-10 Practical Examples

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

## 3.04 Some Example Settings

- Command Palette, Daily Notes, Starred Notes, Random Notes, Sync Status, Tag Pane.

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

---

## 3.05 Useful CSS Selectors Compilations

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

### 3.05-01 Accent Presets

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

### 3.05-01 Translucent Modals

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

---

## 3.06 Style Settings Integrations

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

### 3.06-01 Add This To Styles Setting For Scrollbar Customization

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


### 3.06-02 Example From [Purple Mushroom Fantasy](https://github.com/breakthebull/pmf)

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

---

# 4.01 CSS Snippets (Copy-Paste Ready)

Here are beginner-friendly CSS snippets you can drop into your **CSS Snippets folder** (`Settings → Appearance → CSS snippets`). Each is self-contained and works immediately when toggled on!


## 4.02 Visual Enhancements

### 1. **Colored Blockquotes**
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

---

### 2. **Rounded Corners Everywhere**
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

---

### 3. **Custom Scrollbar**
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

## 4.03 Editor & Reading Improvements

### 4. **Wider Editor (More Writing Space)**
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

---

### 5. **Line Numbers in Editor**
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

---

### 6. **Focus Mode (Dim Other Lines)**
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

## 4.04 Tag & Link Styling

### 7. **Pretty Tags**
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

---

### 8. **Underline Internal Links**
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

## 4.05 Status Bar & Interface

### 9. **Hide Status Bar**
Cleans up the bottom of the screen.

```css
/* Hide status bar completely */
.status-bar {
  display: none !important;
}
```

---

### 10. **Semi-Transparent Sidebars**
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

## 4.06 Callouts & Highlights

### 11. **Highlight Search Results**
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

---

### 12. **Custom Highlight Color**
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

## 4.07 Task & List Tweaks

### 13. **Bigger Checkboxes**
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

---

### 14. **Bullet Point Colors**
Adds color to unordered list bullets.

```css
/* Colored bullet points */
ul > li::marker {
  color: var(--interactive-accent) !important;
  font-weight: bold !important;
}
```

## 4.08 Minimal Mode Helpers

### 15. **Hide Title Bar**
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

---

### 16. **Hide Folder Pane Icons**
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

## 4.09 Bonus: Quick Theme Switcher Helper

### 17. **Dark/Light Mode Toggle Button**
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

---

# 5.01 How to Use These Snippets

1. **Create a new file** in your vault's `.obsidian/snippets/` folder
2. **Name it** something descriptive (e.g., `pretty-tags.css`)
3. **Paste the CSS** code inside
4. **Go to Settings → Appearance → CSS snippets**
5. **Toggle it on** (refresh if needed with `Ctrl+R` / `Cmd+R`)

###  5.01-01 Tips

- **Test one at a time** to avoid conflicts
- **Use `!important`** to override Obsidian's default styles
- **Use CSS variables** like `var(--interactive-accent)` to match your theme
- **Comment your code** so you remember what each snippet does
- **Backup your snippets** folder when switching devices
