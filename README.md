# VS Code Cursive Font Setup

A reusable and developer-friendly **Visual Studio Code configuration** for using the **Victor Mono** programming font with italic/cursive comments, italic function parameters, font ligatures, and the GitHub Dark Dimmed theme.

This repository is intended to make the VS Code editor appearance easy to reproduce on a **new computer, fresh OS installation, or another developer's system** without manually configuring every setting again.

---

## Overview

This repository provides a workspace-level VS Code configuration that includes:

* **Victor Mono** as the primary coding font
* Italic/cursive styling for comments
* Italic styling for function and method parameters
* Font ligatures
* Regular font weight for normal code
* GitHub Dark Dimmed editor theme
* Fallback fonts when Victor Mono is unavailable
* Workspace-specific VS Code settings
* Setup documentation for new developers

The repository does **not** contain the Victor Mono font files. The font must be installed separately on each computer.

---

## Features

### Victor Mono

The configuration uses Victor Mono as the primary editor font.

```text
Victor Mono
```

Fallback fonts are also configured:

```text
Consolas
Courier New
monospace
```

This means VS Code will use Victor Mono when it is installed and automatically fall back to another available font when it is not.

---

### Cursive / Italic Comments

Comments are displayed using the italic variant of Victor Mono.

Example:

```javascript
// Fetch user information from the API

const user = await fetchUser();
```

The comment will appear in the italic/cursive style while the actual code remains in the regular style.

---

### Italic Function Parameters

Function and method parameters are configured to use italic styling.

Example:

```javascript
function getUser(userId) {
    return userId;
}
```

The `userId` parameter will use the italic variant of Victor Mono.

---

### Font Ligatures

Font ligatures are enabled:

```json
"editor.fontLigatures": true
```

This allows Victor Mono to render supported programming characters using its ligature design.

For example, combinations such as:

```text
=>  !=  ===  >=  <=
```

may be rendered using the font's ligature support.

Ligature rendering depends on the selected font and the programming language.

---

### GitHub Dark Dimmed Theme

The workspace uses:

```text
GitHub Dark Dimmed
```

This provides a dark editor appearance that works well with the Victor Mono font and italic syntax styling.

---

## Repository Structure

```text
vscode-cursive-font/
│
├── .vscode/
│   └── settings.json
│
├── README.md
│
└── .gitignore
```

### `.vscode/settings.json`

Contains the workspace-level VS Code configuration.

### `README.md`

Contains installation instructions, configuration details, troubleshooting steps, and usage information.

### `.gitignore`

Prevents temporary files, operating-system files, logs, and other unnecessary files from being committed.

---

# Prerequisites

Before using this configuration, make sure the following are installed:

1. Visual Studio Code
2. Git
3. Victor Mono font

---

# 1. Install Visual Studio Code

Install the latest stable version of Visual Studio Code on your computer.

After installation, verify that VS Code opens correctly.

You can check the installed version from the terminal:

```bash
code --version
```

If the `code` command is not available, you can still open the repository manually from VS Code.

---

# 2. Install Git

Git is required to clone this repository.

Verify the installation:

```bash
git --version
```

If Git is installed correctly, the command will display the installed Git version.

---

# 3. Install Victor Mono

Victor Mono is required for the intended cursive/italic coding appearance.

The font is **not included in this repository**.

Each developer must install Victor Mono separately on their computer.

## Windows Installation

1. Download the Victor Mono font.
2. Extract the downloaded ZIP file.
3. Open the extracted folder.
4. Select the font files.
5. Right-click the selected files.
6. Choose **Install** or **Install for all users**.
7. Wait for the installation to complete.
8. Restart Visual Studio Code.

After installing the font, VS Code should be able to detect:

```text
Victor Mono
```

### Important

Do not add the Victor Mono `.ttf` or `.otf` files to this repository.

The repository contains the VS Code configuration only.

---

# 4. Clone the Repository

Open a terminal and clone the repository:

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
```

Replace:

```text
<YOUR_GITHUB_REPOSITORY_URL>
```

with the actual GitHub repository URL.

For example:

```bash
git clone https://github.com/YOUR_USERNAME/vscode-cursive-font.git
```

Move into the project directory:

```bash
cd vscode-cursive-font
```

---

# 5. Open the Repository in VS Code

If the VS Code `code` command is available, run:

```bash
code .
```

Alternatively:

1. Open Visual Studio Code.
2. Select **File → Open Folder**.
3. Select the cloned `vscode-cursive-font` folder.
4. Open the project.

Once the repository is opened, VS Code will detect:

```text
.vscode/settings.json
```

and apply the workspace settings.

---

# 6. VS Code Configuration

The main configuration file is:

```text
.vscode/settings.json
```

The configuration is intentionally stored inside the repository so that it can be shared through Git.

This means another developer does not need to manually configure the same editor settings.

---

# 7. Font Configuration

The primary font is configured using:

```json
"editor.fontFamily": "'Victor Mono', Consolas, 'Courier New', monospace"
```

The font priority is:

```text
1. Victor Mono
2. Consolas
3. Courier New
4. monospace
```

If Victor Mono is installed, VS Code will use it.

If Victor Mono is unavailable, VS Code will attempt to use the next available fallback font.

---

# 8. Font Size

The default font size is:

```json
"editor.fontSize": 16
```

This can be changed according to personal preference.

For example:

```json
"editor.fontSize": 15
```

or:

```json
"editor.fontSize": 17
```

The repository uses `16` as the default because it provides a good balance between readability and the amount of code visible on screen.

---

# 9. Font Weight

The default font weight is:

```json
"editor.fontWeight": "400"
```

`400` represents regular font weight.

This is intentional because the desired appearance uses italic/cursive styling for selected syntax rather than making the entire editor bold.

Avoid using:

```json
"editor.fontWeight": "bold"
```

unless you specifically want all code to appear bold.

---

# 10. Font Ligatures

Font ligatures are enabled with:

```json
"editor.fontLigatures": true
```

This allows Victor Mono to use its programming ligature characters where supported.

For example:

```javascript
const isValid = value >= 10 && value !== null;
```

The visual appearance of operators may be modified by the font's ligature support.

---

# 11. Cursive / Italic Styling

The italic styling is controlled using:

```json
"editor.tokenColorCustomizations"
```

and TextMate scopes.

The configuration targets:

```text
comment
variable.parameter
```

These scopes are assigned:

```json
"fontStyle": "italic"
```

---

## Comments

The following scope targets comments:

```text
comment
```

Example:

```javascript
// Fetch user information from the server

const user = await fetchUser();
```

The comment will use Victor Mono's italic variant.

---

## Function Parameters

The following scope targets function and method parameters:

```text
variable.parameter
```

Example:

```javascript
function getUser(userId) {
    return userId;
}
```

The `userId` parameter is configured to use italic styling.

---

# 12. Preventing Unwanted Italic Styling

Some syntax scopes are explicitly reset to regular styling:

```text
invalid
keyword.operator
constant.numeric.css
keyword.other.unit.px.css
constant.numeric.decimal.js
constant.numeric.json
```

These scopes use:

```json
"fontStyle": ""
```

This prevents certain operators and numeric values from unnecessarily inheriting italic styling.

For example:

```javascript
const age = 25;
const isAdult = age >= 18;
```

The numeric values and operators should remain visually normal.

---

# 13. Complete `.vscode/settings.json`

The complete configuration used by this repository is:

```jsonc
{
    "editor.fontFamily": "'Victor Mono', Consolas, 'Courier New', monospace",
    "editor.fontSize": 16,
    "editor.fontWeight": "400",
    "editor.fontLigatures": true,

    // Makes comments and function parameters italic
    "editor.tokenColorCustomizations": {
        "textMateRules": [
            {
                "scope": [
                    "comment",
                    "variable.parameter"
                ],
                "settings": {
                    "fontStyle": "italic"
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

    "workbench.colorTheme": "GitHub Dark Dimmed"
}
```

---

# 14. Theme Configuration

The workspace uses:

```json
"workbench.colorTheme": "GitHub Dark Dimmed"
```

This theme provides the dark editor appearance used with this configuration.

If the theme is not available in your VS Code installation, you can install it through the VS Code Extensions panel or select another theme manually.

Changing the theme will not affect the Victor Mono font configuration.

---

# 15. Verify the Configuration

After installing Victor Mono and opening the repository, create or open a JavaScript or TypeScript file.

Add the following:

```javascript
// This comment should appear italic/cursive

function getUser(userId) {
    const user = {
        id: userId,
        name: "John",
        age: 25
    };

    return user;
}
```

The expected appearance is:

```text
Comments            → Italic / cursive
Function parameters → Italic / cursive
Normal code         → Regular
Numbers             → Regular
Operators           → Regular
Font                → Victor Mono
Theme               → GitHub Dark Dimmed
```

---

# 16. Troubleshooting

## Victor Mono Is Not Being Applied

If the editor is not using Victor Mono:

### Step 1

Confirm that Victor Mono is installed.

### Step 2

Completely close VS Code.

### Step 3

Open VS Code again.

### Step 4

Reload the VS Code window.

Open the Command Palette:

```text
Ctrl + Shift + P
```

Search:

```text
Developer: Reload Window
```

Press Enter.

### Step 5

Open VS Code Settings and search for:

```text
Font Family
```

Confirm that the configuration contains:

```text
'Victor Mono'
```

---

# 17. Check the Installed Font

On Windows, open:

```text
Settings → Personalization → Fonts
```

Search for:

```text
Victor Mono
```

If it appears in the installed fonts list, the font is installed correctly.

If it does not appear, reinstall the font and restart VS Code.

---

# 18. Cursive Comments Are Not Working

If Victor Mono is working but comments are not italic:

1. Open the repository in VS Code.
2. Open `.vscode/settings.json`.
3. Confirm that the `textMateRules` configuration exists.
4. Make sure the comment scope is:

```text
comment
```

5. Reload the VS Code window.

The relevant configuration is:

```json
{
    "scope": [
        "comment",
        "variable.parameter"
    ],
    "settings": {
        "fontStyle": "italic"
    }
}
```

---

# 19. Code Is Completely Bold

If all your code appears bold, check:

```json
"editor.fontWeight": "400"
```

Do not use:

```json
"editor.fontWeight": "bold"
```

The `400` setting keeps normal code at regular weight.

---

# 20. New Computer Setup

This repository is specifically designed to make setup easy when moving to a new computer.

Follow these steps:

### Step 1 — Install Git

```bash
git --version
```

### Step 2 — Install VS Code

Install Visual Studio Code.

### Step 3 — Install Victor Mono

Install the font on the operating system.

### Step 4 — Clone the repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
```

### Step 5 — Open the project

```bash
cd vscode-cursive-font
code .
```

### Step 6 — Reload VS Code if necessary

Use:

```text
Ctrl + Shift + P
```

and run:

```text
Developer: Reload Window
```

### Step 7 — Verify

Open a JavaScript or TypeScript file and check the font and italic styling.

---

# 21. Setup for Another Developer

Another developer can use this repository without manually configuring their global VS Code settings.

They only need to:

1. Install VS Code.
2. Install Git.
3. Install Victor Mono.
4. Clone this repository.
5. Open the repository in VS Code.

Commands:

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd vscode-cursive-font
code .
```

The workspace configuration will automatically be loaded from:

```text
.vscode/settings.json
```

---

# 22. Workspace Settings vs Global Settings

This repository uses:

```text
.vscode/settings.json
```

rather than requiring developers to modify their global VS Code settings.

### Workspace settings

Stored inside the project:

```text
project/
└── .vscode/
    └── settings.json
```

These settings apply when the specific repository is opened.

### User settings

Global settings are stored in the developer's personal VS Code configuration.

This repository does not require developers to replace or modify their entire global `settings.json`.

This makes the configuration safer and easier to share.

---

# 23. Why the Font Is Not Stored in Git

The Victor Mono font is intentionally not included in this repository.

The repository stores:

```text
VS Code configuration
```

while the operating system stores:

```text
Victor Mono font
```

The setup therefore works like this:

```text
GitHub Repository
        │
        ├── .vscode/settings.json
        │       ├── Font Family
        │       ├── Font Size
        │       ├── Font Weight
        │       ├── Font Ligatures
        │       ├── Italic Comments
        │       └── Italic Parameters
        │
        └── README.md
                └── Installation Instructions

Developer Computer
        │
        └── Victor Mono Font
```

This keeps the repository lightweight and avoids distributing font files unnecessarily.

---

# 24. Git Configuration

The `.gitignore` file excludes temporary and unnecessary files such as:

```text
.DS_Store
Thumbs.db
*.log
*.tmp
*.bak
```

However, `.vscode/settings.json` remains tracked.

Do not add:

```text
.vscode/
```

to `.gitignore`.

---

# 25. Updating the Configuration

If you change the VS Code configuration in the future:

```bash
git status
```

Review the changes:

```bash
git diff
```

Then commit:

```bash
git add .vscode/settings.json
git commit -m "Update VS Code editor configuration"
```

Push the changes:

```bash
git push
```

Other developers can then update their local configuration:

```bash
git pull
```

---

# 26. Recommended Customizations

You can customize the configuration according to your preference.

### Change font size

```json
"editor.fontSize": 17
```

### Disable ligatures

```json
"editor.fontLigatures": false
```

### Disable italic comments

Change:

```json
"fontStyle": "italic"
```

to:

```json
"fontStyle": ""
```

### Use italic and bold comments

```json
"fontStyle": "italic bold"
```

The recommended setting for the intended appearance is:

```json
"fontStyle": "italic"
```

---

# 27. Recommended Default Configuration

| Setting             | Value              |
| ------------------- | ------------------ |
| Font                | Victor Mono        |
| Font Size           | 16                 |
| Font Weight         | 400                |
| Font Ligatures      | Enabled            |
| Comments            | Italic             |
| Function Parameters | Italic             |
| Theme               | GitHub Dark Dimmed |
| Configuration Type  | Workspace          |

---

# 28. Quick Setup

For an experienced developer, the complete setup is:

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd vscode-cursive-font
code .
```

Before opening the project, make sure **Victor Mono is installed** on the system.

---

# 29. Repository Maintenance

Keep this repository focused on VS Code editor configuration.

Recommended files:

```text
.vscode/settings.json
README.md
.gitignore
```

Avoid committing:

* Font files
* Personal VS Code settings unrelated to this setup
* API keys
* Passwords
* Machine-specific configuration
* Temporary files
* Build output
* Logs

This keeps the repository reusable for yourself and other developers.

---

# License

This repository contains VS Code configuration and documentation.

Victor Mono is not included in this repository. Victor Mono remains subject to its own license and distribution terms.

When downloading or installing Victor Mono, follow the font's official licensing and distribution requirements.
