# VS Code Cursive Font Setup

A reusable and developer-friendly **Visual Studio Code configuration** for creating a clean and modern coding environment using **Victor Mono**, italic/cursive syntax styling, font ligatures, GitHub Dark Dimmed, Material Icon Theme, and Fluent Icons.

This repository is designed to make the same VS Code appearance easy to reproduce on a **new computer, fresh OS installation, or another developer's system** without manually configuring everything again.

---

## Overview

This repository provides a reusable VS Code workspace configuration with:

* **Victor Mono** as the primary coding font
* Italic and bold styling for selected syntax elements
* Italic/cursive comments
* Italic function and method parameters
* Italic keywords
* Italic constants
* Italic class names and related syntax
* Font ligatures
* Regular font weight for the editor
* **GitHub Dark Dimmed** color theme
* **Material Icon Theme** for file and folder icons
* **Fluent Icons** for VS Code product icons
* Workspace-level VS Code settings
* Documentation for setting up the environment on another computer

The repository contains the **VS Code configuration**, not the Victor Mono font files.

---

# Preview

The setup is intended to produce a VS Code appearance similar to the demo below:

![VS Code Cursive Font Setup Demo](assets/vscode-cursive-font-demo.png)

The demo shows:

* Victor Mono font
* Italic/cursive comments
* Italic function parameters
* Normal operators and numbers
* Font ligatures
* GitHub Dark Dimmed
* The overall configured VS Code appearance

---

# Features

## 1. Victor Mono Font

The primary editor font is:

```text
Victor Mono
```

Fallback fonts are configured as:

```text
Consolas
Courier New
monospace
```

The configuration is:

```json
"editor.fontFamily": "'Victor Mono', Consolas, 'Courier New', monospace"
```

If Victor Mono is installed, VS Code will use it.

If Victor Mono is unavailable, VS Code will use the next available fallback font.

---

## 2. Italic and Bold Syntax Styling

Selected syntax scopes are configured with:

```json
"fontStyle": "italic bold"
```

This provides the cursive/italic appearance for selected parts of the code while keeping the overall editor readable.

The configuration applies to scopes such as:

```text
comment
entity.attribute.name
entity.other.attribute-name
entity.other.attribute-name.class
entity.other.attribute-name.id
entity.name.type.class
keyword
constant
storage.modifier
storage.type
storage.type.function
storage.type.class
storage.type.class.js
variable.parameter
```

This allows different code elements to use Victor Mono's italic style.

---

## 3. Cursive / Italic Comments

Comments are included in the italic styling.

Example:

```javascript
// Fetch user information from the API

const user = await fetchUser();
```

The comment will use the italic variant of Victor Mono.

---

## 4. Italic Function Parameters

Function and method parameters are included in the italic styling.

Example:

```javascript
function getUser(userId) {
    return userId;
}
```

The `userId` parameter is styled using the italic font variant.

---

## 5. Italic Keywords

Keywords are included in the styling rules:

```text
keyword
```

Examples include syntax such as:

```javascript
import
export
return
if
else
async
await
```

The final appearance depends on how the selected language's syntax grammar maps each token.

---

## 6. Italic Constants

The configuration also includes:

```text
constant
```

This can affect tokens such as constants, strings, numbers, booleans, and other language-specific constant scopes depending on the language grammar.

---

## 7. Class and Attribute Styling

The configuration also includes:

```text
entity.attribute.name
entity.other.attribute-name
entity.other.attribute-name.class
entity.other.attribute-name.id
entity.name.type.class
```

This allows class names and certain attribute-related syntax elements to inherit the italic/bold appearance.

---

## 8. Storage and Type Styling

The following scopes are included:

```text
storage.modifier
storage.type
storage.type.function
storage.type.class
storage.type.class.js
```

These can affect syntax such as:

```javascript
static
class
function
```

and language-specific storage/type declarations.

---

## 9. Font Ligatures

Font ligatures are enabled with:

```json
"editor.fontLigatures": true
```

Victor Mono supports programming ligatures for supported character combinations.

For example:

```text
=>  !=  !==  ===  >=  <=
```

This can make code visually cleaner and easier to scan.

The exact rendering depends on the language and the font.

---

# VS Code Appearance

The configuration uses three visual settings:

```json
"workbench.colorTheme": "GitHub Dark Dimmed",
"workbench.iconTheme": "material-icon-theme",
"workbench.productIconTheme": "fluent-icons"
```

These control different parts of the VS Code interface.

| Setting                      | Purpose                         |
| ---------------------------- | ------------------------------- |
| `workbench.colorTheme`       | Main editor and UI color theme  |
| `workbench.iconTheme`        | File and folder icons           |
| `workbench.productIconTheme` | VS Code interface/product icons |

---

# Required VS Code Extensions

Install the following extensions to reproduce the complete appearance.

## 1. GitHub Theme

**Extension:** GitHub Theme

**Publisher:** GitHub

**Extension ID:**

```text
GitHub.github-vscode-theme
```

The GitHub Theme extension provides GitHub's color themes, including **GitHub Dark Dimmed**.

Marketplace:

https://marketplace.visualstudio.com/items?itemName=GitHub.github-vscode-theme

Install it from the VS Code Extensions panel by searching:

```text
GitHub Theme
```

---

## 2. Material Icon Theme

**Extension:** Material Icon Theme

**Publisher:** Philipp Kief

**Extension ID:**

```text
PKief.material-icon-theme
```

Material Icon Theme provides file and folder icons for Visual Studio Code.

Marketplace:

https://marketplace.visualstudio.com/items?itemName=PKief.material-icon-theme

Install it from the VS Code Extensions panel by searching:

```text
Material Icon Theme
```

After installation, the following setting enables it:

```json
"workbench.iconTheme": "material-icon-theme"
```

---

## 3. Fluent Icons

**Extension:** Fluent Icons

**Publisher:** Miguel Solorio

**Extension ID:**

```text
miguelsolorio.fluent-icons
```

Fluent Icons provides Fluent-style product icons for Visual Studio Code.

Marketplace:

https://marketplace.visualstudio.com/items?itemName=miguelsolorio.fluent-icons

Install it from the VS Code Extensions panel by searching:

```text
Fluent Icons
```

After installation, the following setting enables it:

```json
"workbench.productIconTheme": "fluent-icons"
```

---

# Required Font

## Victor Mono

Victor Mono is a programming font with an italic style that gives the cursive appearance used by this configuration.

### Official Website

https://rubjo.github.io/victor-mono/

Download and install the font before opening VS Code.

---

# Prerequisites

Before using this setup, make sure the following are installed:

1. Visual Studio Code
2. Git
3. Victor Mono
4. GitHub Theme extension
5. Material Icon Theme extension
6. Fluent Icons extension

---

# Installation Guide

## Step 1 — Install Visual Studio Code

Install the latest stable version of Visual Studio Code.

You can verify the installation with:

```bash
code --version
```

If the `code` command is not available, you can open VS Code normally and use **File → Open Folder**.

---

## Step 2 — Install Git

Install Git if it is not already installed.

Verify it with:

```bash
git --version
```

---

## Step 3 — Download Victor Mono

Open the official Victor Mono website:

https://rubjo.github.io/victor-mono/

Download the font package.

---

## Step 4 — Install Victor Mono on Windows

1. Extract the downloaded ZIP file.
2. Open the extracted folder.
3. Select the Victor Mono font files.
4. Right-click the files.
5. Select **Install** or **Install for all users**.
6. Wait until the font installation is complete.
7. Restart VS Code.

After installation, your system should recognize:

```text
Victor Mono
```

### Important

Do not commit Victor Mono font files to this repository.

The repository stores the configuration only.

---

# Step 5 — Install the VS Code Extensions

Open Visual Studio Code.

Press:

```text
Ctrl + Shift + X
```

This opens the Extensions panel.

Install the following:

### GitHub Theme

```text
GitHub Theme
```

### Material Icon Theme

```text
Material Icon Theme
```

### Fluent Icons

```text
Fluent Icons
```

These extensions provide the themes and icon sets referenced by the repository configuration.

---

# Step 6 — Clone the Repository

Open a terminal:

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
```

Example:

```bash
git clone https://github.com/YOUR_USERNAME/vscode-cursive-font.git
```

Move into the repository:

```bash
cd vscode-cursive-font
```

---

# Step 7 — Open the Repository in VS Code

Run:

```bash
code .
```

Or open VS Code manually:

1. Open Visual Studio Code.
2. Select **File → Open Folder**.
3. Select the cloned repository.
4. Open the folder.

VS Code will detect:

```text
.vscode/settings.json
```

and apply the workspace configuration.

---

# Manual Configuration in VS Code

The repository provides `.vscode/settings.json`, but you can also configure the same setup manually in your personal VS Code settings.

This is useful when you want the configuration to apply to **all projects**, not only this repository.

---

# Step 1 — Open `settings.json`

Open Visual Studio Code.

Press:

```text
Ctrl + Shift + P
```

Search for:

```text
Preferences: Open User Settings (JSON)
```

Press **Enter**.

VS Code will open your personal `settings.json` file.

---

# Alternative Method

You can also:

1. Open VS Code.
2. Open **File → Preferences → Settings**.
3. Find the **Open Settings (JSON)** icon in the top-right corner.
4. Click it.

This will open your `settings.json`.

---

# Step 2 — Add the Configuration

Add the following configuration to your `settings.json`:

```jsonc
{
    "editor.fontFamily": "'Victor Mono', Consolas, 'Courier New', monospace",
    "editor.fontSize": 16,
    "editor.fontWeight": "400",
    "editor.fontLigatures": true,

    // Makes selected syntax italic and bold
    "editor.tokenColorCustomizations": {
        "textMateRules": [
            {
                "scope": [
                    "comment",
                    "entity.attribute.name",
                    "entity.other.attribute-name",
                    "entity.other.attribute-name.class",
                    "entity.other.attribute-name.id",
                    "entity.name.type.class",
                    "keyword",
                    "constant",
                    "storage.modifier",
                    "storage.type",
                    "storage.type.function",
                    "storage.type.class",
                    "storage.type.class.js",
                    "variable.parameter"
                ],
                "settings": {
                    "fontStyle": "italic bold"
                }
            },
            {
                "scope": [
                    "invalid",
                    "keyword.operator",
                    "constant.numeric.css",
                    "keyword.other.unit.px.css",
                    "constant.numeric.decimal.js",
                    "constant.numeric.json"
                ],
                "settings": {
                    "fontStyle": ""
                }
            }
        ]
    },

    "workbench.colorTheme": "GitHub Dark Dimmed",
    "workbench.iconTheme": "material-icon-theme",
    "workbench.productIconTheme": "fluent-icons"
}
```

---

# Important: Existing `settings.json`

If you already have other VS Code settings, do **not** delete your existing configuration.

Merge the required properties into the existing `settings.json`.

For example, if your current configuration is:

```json
{
    "editor.fontSize": 14,
    "git.enabled": true
}
```

keep those settings and add the new configuration.

You should end up with something like:

```jsonc
{
    "editor.fontSize": 16,
    "git.enabled": true,

    "editor.fontFamily": "'Victor Mono', Consolas, 'Courier New', monospace",
    "editor.fontWeight": "400",
    "editor.fontLigatures": true,

    // Makes selected syntax italic and bold
    "editor.tokenColorCustomizations": {
        "textMateRules": [
            {
                "scope": [
                    "comment",
                    "entity.attribute.name",
                    "entity.other.attribute-name",
                    "entity.other.attribute-name.class",
                    "entity.other.attribute-name.id",
                    "entity.name.type.class",
                    "keyword",
                    "constant",
                    "storage.modifier",
                    "storage.type",
                    "storage.type.function",
                    "storage.type.class",
                    "storage.type.class.js",
                    "variable.parameter"
                ],
                "settings": {
                    "fontStyle": "italic bold"
                }
            },
            {
                "scope": [
                    "invalid",
                    "keyword.operator",
                    "constant.numeric.css",
                    "keyword.other.unit.px.css",
                    "constant.numeric.decimal.js",
                    "constant.numeric.json"
                ],
                "settings": {
                    "fontStyle": ""
                }
            }
        ]
    },

    "workbench.colorTheme": "GitHub Dark Dimmed",
    "workbench.iconTheme": "material-icon-theme",
    "workbench.productIconTheme": "fluent-icons"
}
```

---

# Complete Workspace Configuration

The repository's `.vscode/settings.json` should contain:

```jsonc
{
    "editor.fontFamily": "'Victor Mono', Consolas, 'Courier New', monospace",
    "editor.fontSize": 16,
    "editor.fontWeight": "400",
    "editor.fontLigatures": true,

    // Makes selected syntax italic and bold
    "editor.tokenColorCustomizations": {
        "textMateRules": [
            {
                "scope": [
                    "comment",
                    "entity.attribute.name",
                    "entity.other.attribute-name",
                    "entity.other.attribute-name.class",
                    "entity.other.attribute-name.id",
                    "entity.name.type.class",
                    "keyword",
                    "constant",
                    "storage.modifier",
                    "storage.type",
                    "storage.type.function",
                    "storage.type.class",
                    "storage.type.class.js",
                    "variable.parameter"
                ],
                "settings": {
                    "fontStyle": "italic bold"
                }
            },
            {
                "scope": [
                    "invalid",
                    "keyword.operator",
                    "constant.numeric.css",
                    "keyword.other.unit.px.css",
                    "constant.numeric.decimal.js",
                    "constant.numeric.json"
                ],
                "settings": {
                    "fontStyle": ""
                }
            }
        ]
    },

    "workbench.colorTheme": "GitHub Dark Dimmed",
    "workbench.iconTheme": "material-icon-theme",
    "workbench.productIconTheme": "fluent-icons"
}
```

---

# Verify the Setup

Create or open a JavaScript or TypeScript file and add:

```javascript
// This comment should appear italic/cursive

async function getUser(userId) {
    const response = await fetch(
        `https://example.com/users/${userId}`
    );

    if (!response.ok) {
        throw new Error("Failed to fetch user");
    }

    return response.json();
}
```

Check the following:

```text
Font                   → Victor Mono
Comments               → Italic / bold
Function parameters    → Italic / bold
Keywords               → Italic / bold
Class names            → Italic / bold
Operators              → Regular
Numbers                → Regular
Font ligatures         → Enabled
Color theme            → GitHub Dark Dimmed
File icons             → Material Icon Theme
Product icons          → Fluent Icons
```

---

# Troubleshooting

## Victor Mono Is Not Being Applied

If the editor is not using Victor Mono:

### Step 1 — Confirm Victor Mono Is Installed

On Windows:

```text
Settings → Personalization → Fonts
```

Search for:

```text
Victor Mono
```

If it is not listed, download it from:

https://rubjo.github.io/victor-mono/

and install it again.

---

### Step 2 — Completely Close VS Code

Close all VS Code windows.

Make sure VS Code is completely closed before continuing.

---

### Step 3 — Open VS Code Again

Launch Visual Studio Code again.

---

### Step 4 — Reload the VS Code Window

Open the Command Palette:

```text
Ctrl + Shift + P
```

Search:

```text
Developer: Reload Window
```

Press **Enter**.

---

### Step 5 — Open `settings.json`

Open:

```text
Ctrl + Shift + P
```

Search:

```text
Preferences: Open User Settings (JSON)
```

Press **Enter**.

Confirm that you have:

```json
"editor.fontFamily": "'Victor Mono', Consolas, 'Courier New', monospace"
```

Also confirm:

```json
"editor.fontLigatures": true
```

and:

```json
"editor.fontWeight": "400"
```

---

### Step 6 — Check Font Family

Open:

```text
Settings → Text Editor → Font
```

Find:

```text
Font Family
```

Confirm that it contains:

```text
'Victor Mono'
```

---

# GitHub Dark Dimmed Is Not Working

Make sure the **GitHub Theme** extension is installed.

Then confirm your configuration contains:

```json
"workbench.colorTheme": "GitHub Dark Dimmed"
```

Open the Command Palette:

```text
Ctrl + Shift + P
```

Search:

```text
Preferences: Color Theme
```

Select:

```text
GitHub Dark Dimmed
```

The GitHub Theme extension provides the GitHub Dark Dimmed theme.

---

# Material Icons Are Not Working

Make sure the **Material Icon Theme** extension is installed.

Confirm:

```json
"workbench.iconTheme": "material-icon-theme"
```

You can also activate it manually:

```text
Ctrl + Shift + P
```

Search:

```text
Material Icons: Activate Icon Theme
```

Then select **Material Icon Theme**.

---

# Fluent Icons Are Not Working

Make sure the **Fluent Icons** extension is installed.

Confirm:

```json
"workbench.productIconTheme": "fluent-icons"
```

Then reload VS Code:

```text
Ctrl + Shift + P
→ Developer: Reload Window
```

The Fluent Icons extension uses the product icon theme identifier:

```text
fluent-icons
```

and is published as `miguelsolorio.fluent-icons`.

---

# Cursive Styling Is Not Working

If Victor Mono is working but the italic styling is not:

1. Open `.vscode/settings.json`.
2. Check `editor.tokenColorCustomizations`.
3. Confirm the `textMateRules` are present.
4. Confirm the desired scopes are included.
5. Confirm:

```json
"fontStyle": "italic bold"
```

Reload VS Code after changing the settings.

---

# Code Is Completely Bold

If everything appears bold, make sure the editor configuration contains:

```json
"editor.fontWeight": "400"
```

Do not use:

```json
"editor.fontWeight": "bold"
```

The individual syntax scopes are responsible for the italic/bold appearance.

---

# Setting Up on a New Computer

Use the following process whenever moving to another computer.

## 1. Install VS Code

Install Visual Studio Code.

## 2. Install Git

Verify:

```bash
git --version
```

## 3. Install Victor Mono

Download from:

https://rubjo.github.io/victor-mono/

Install the font.

## 4. Install VS Code Extensions

Install:

```text
GitHub Theme
Material Icon Theme
Fluent Icons
```

## 5. Clone the Repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
```

## 6. Open the Repository

```bash
cd vscode-cursive-font
code .
```

## 7. Reload VS Code

If necessary:

```text
Ctrl + Shift + P
→ Developer: Reload Window
```

## 8. Verify

Confirm:

```text
Victor Mono             → Working
Cursive syntax          → Working
GitHub Dark Dimmed      → Applied
Material icons          → Applied
Fluent product icons    → Applied
Font ligatures          → Enabled
```

---

# Setup for Another Developer

Another developer can reproduce the same environment by following:

```text
1. Install VS Code
2. Install Git
3. Download and install Victor Mono
4. Install GitHub Theme
5. Install Material Icon Theme
6. Install Fluent Icons
7. Clone this repository
8. Open the repository in VS Code
```

Commands:

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd vscode-cursive-font
code .
```

The workspace configuration will automatically load from:

```text
.vscode/settings.json
```

---

# Workspace Settings vs User Settings

This repository uses:

```text
.vscode/settings.json
```

These are workspace settings.

They apply when this repository is opened.

## Workspace Settings

```text
project/
└── .vscode/
    └── settings.json
```

## User Settings

These are the developer's global VS Code settings and apply across projects.

You can use either approach:

* Use the repository's `.vscode/settings.json` for project-specific configuration.
* Copy the configuration into User `settings.json` if you want the appearance across all projects.

---

# Why the Font Is Not Stored in Git

Victor Mono is intentionally not included in the repository.

The repository stores:

```text
VS Code configuration
```

The operating system stores:

```text
Victor Mono font
```

The setup therefore works like this:

```text
GitHub Repository
        │
        ├── .vscode/settings.json
        │       ├── Font
        │       ├── Font Styling
        │       ├── Ligatures
        │       ├── Color Theme
        │       ├── File Icon Theme
        │       └── Product Icon Theme
        │
        └── README.md
                └── Installation Instructions

Developer Computer
        │
        ├── Victor Mono
        ├── GitHub Theme
        ├── Material Icon Theme
        └── Fluent Icons
```

This keeps the repository lightweight and focused on the editor configuration.

---

# Git Configuration

The `.gitignore` file excludes unnecessary operating-system and temporary files.

Examples:

```text
.DS_Store
Thumbs.db
Desktop.ini
*.log
*.tmp
*.temp
*.bak
*.swp
```

The following must **not** be ignored:

```text
.vscode/settings.json
```

Do not add:

```text
.vscode/
```

to `.gitignore`.

The workspace configuration needs to remain tracked by Git.

---

# Updating the Configuration

When you modify the VS Code configuration:

Check the status:

```bash
git status
```

Review changes:

```bash
git diff
```

Stage the settings:

```bash
git add .vscode/settings.json
```

Commit:

```bash
git commit -m "Update VS Code editor configuration"
```

Push:

```bash
git push
```

Other developers can receive the updated configuration using:

```bash
git pull
```

---

# Recommended Customizations

## Change Font Size

```json
"editor.fontSize": 17
```

## Disable Ligatures

```json
"editor.fontLigatures": false
```

## Disable Italic Styling

Change:

```json
"fontStyle": "italic bold"
```

to:

```json
"fontStyle": ""
```

## Use Italic Without Bold

Change:

```json
"fontStyle": "italic bold"
```

to:

```json
"fontStyle": "italic"
```

## Change Color Theme

Replace:

```json
"workbench.colorTheme": "GitHub Dark Dimmed"
```

with the name of another installed VS Code theme.

---

# Recommended Configuration

| Setting            | Value               |
| ------------------ | ------------------- |
| Font               | Victor Mono         |
| Font Size          | 16                  |
| Font Weight        | 400                 |
| Font Ligatures     | Enabled             |
| Selected Syntax    | Italic + Bold       |
| Operators          | Regular             |
| Numbers            | Regular             |
| Color Theme        | GitHub Dark Dimmed  |
| File Icon Theme    | Material Icon Theme |
| Product Icon Theme | Fluent Icons        |
| Configuration      | Workspace           |

---

# Quick Setup

For an experienced developer:

### 1. Install Victor Mono

https://rubjo.github.io/victor-mono/

### 2. Install Extensions

```text
GitHub Theme
Material Icon Theme
Fluent Icons
```

### 3. Clone the repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
```

### 4. Open the project

```bash
cd vscode-cursive-font
code .
```

### 5. Reload VS Code if necessary

```text
Ctrl + Shift + P
→ Developer: Reload Window
```

---

# Repository Maintenance

Keep the repository focused on the VS Code configuration.

Recommended structure:

```text
vscode-cursive-font/
│
├── .vscode/
│   └── settings.json
│
├── assets/
│   └── vscode-cursive-font-demo.png
│
├── README.md
│
└── .gitignore
```

Avoid committing:

* Font files
* API keys
* Passwords
* Personal credentials
* Machine-specific configuration
* Temporary files
* Build output
* Logs
* Unrelated personal VS Code settings

This keeps the repository clean, reusable, and easy for other developers to understand.

---

# License

This repository contains VS Code configuration, documentation, and demonstration assets.

Victor Mono is not included in this repository.

Victor Mono remains subject to its own license and distribution terms. Please follow the official Victor Mono project's licensing and distribution requirements when downloading and installing the font.

The referenced VS Code extensions and themes remain subject to their respective licenses and publisher terms.

---

# Author

Maintained as a reusable VS Code developer setup for a clean, modern, and cursive coding experience.

