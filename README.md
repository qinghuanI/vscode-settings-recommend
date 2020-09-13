# settings.json for vscode

可以通过各种设置配置 Visual Studio Code。VScode 编辑器的用户界面和功能行为都可以自定义。

VS Code 提供了两种不同的设置范围:

- **用户设置** - 全局应用于您打开的任何 VS Code 实例的设置。
- **工作区设置** - 存储在工作区中的设置，仅在打开工作区时适用

用户设置针对某一个具体的项目。而工作区设置针对每一个项目。用户设置的优先级大于工作区设置。

## EditorConfig

## Prettier

## ESLint

## StyleLint

## Vuter

## MarkdownLint

## Cspell

## recommend

工作区设置推荐如下

```json
{
// window
  "window.zoomLevel": 0,

  // editor UI
  "editor.fontSize": 16,
  "editor.tabSize": 2,
  "editor.formatOnType": true,
  "editor.fontWeight": "500",
  "editor.formatOnSave": false,
  "editor.suggestSelection": "first",
  "editor.wordWrap": "on",
  // "editor.wrappingColumn": 120,

  // javascript
  "javascript.format.insertSpaceBeforeFunctionParenthesis": true,

  // files
  "files.autoSave": "afterDelay",

  // workbench
  "workbench.colorTheme": "GitHub Light",
  "workbench.sideBar.location": "left",
  "workbench.iconTheme": "material-icon-theme",
  "workbench.colorCustomizations": {
    "terminal.background": "#fff",
    "terminal.foreground": "#303030",
    "terminalCursor.background": "#303030",
    "terminalCursor.foreground": "#303030",
    "terminal.ansiBlack": "#F5F5F5",
    "terminal.ansiBlue": "#6A9FB5",
    "terminal.ansiBrightBlack": "#B0B0B0",
    "terminal.ansiBrightBlue": "#6A9FB5",
    "terminal.ansiBrightCyan": "#75B5AA",
    "terminal.ansiBrightGreen": "#90A959",
    "terminal.ansiBrightMagenta": "#AA759F",
    "terminal.ansiBrightRed": "#AC4142",
    "terminal.ansiBrightWhite": "#151515",
    "terminal.ansiBrightYellow": "#F4BF75",
    "terminal.ansiCyan": "#75B5AA",
    "terminal.ansiGreen": "#90A959",
    "terminal.ansiMagenta": "#AA759F",
    "terminal.ansiRed": "#AC4142",
    "terminal.ansiWhite": "#303030",
    "terminal.ansiYellow": "#F4BF75"
  },

  // Terminal
  "terminal.integrated.lineHeight": 1,
  "terminal.integrated.fontSize": 14,
  "terminal.integrated.fontFamily": "Meslo LG M for Powerline",
  "terminal.integrated.cursorBlinking": true,
  "terminal.integrated.rendererType": "dom",
  "terminal.integrated.cursorStyle": "line",

  //  ESLint
  "eslint.enable": true,
  "editor.codeActionsOnSave": {
    "source.fixAll": true,
    "source.fixAll.eslint": true,
    "source.fixAll.markdownlint": true
  },
  "[javascript]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "editor.formatOnSave": true
  },
  "eslint.validate": ["javascript", "javascriptreact", "vue", "html"],
  "eslint.options": {
    "plugins": ["html"]
  },

  // prettier
  "prettier.tabWidth": 2,
  "prettier.semi": true,
  "prettier.singleQuote": true,
  "prettier.arrowParens": "avoid",
  "prettier.bracketSpacing": true,
  "prettier.trailingComma": "none",
  "prettier.jsxBracketSameLine": false,

  // cspell
  "cSpell.language": "en",
  "cSpell.enabled": true,
  "cSpell.enableFiletypes": [
    "css",
    "git-commit",
    "html",
    "python",
    "go",
    "javascript",
    "javascriptreact",
    "json",
    "jsx-tags",
    "markdown",
    "pug",
    "sass",
    "scss",
    "less",
    "text",
    "yaml",
    "vue"
  ],
  "cSpell.ignorePaths": [
    "node_modules", // this will ignore anything the node_modules directory
    "**/node_modules", // the same for this one
    "**/node_modules/**", // the same for this one
    "node_modules/**", // Doesn't currently work due to how the current working directory is determined.
    "vscode-extension", //
    ".git", // Ignore the .git directory
    "*.dll", // Ignore all .dll files.
    "**/*.dll" // Ignore all .dll files
  ],
  "cSpell.showStatus": true,

  // stylelint
  "stylelint.enable": true,
  "stylelint.autoFixOnSave": true,

  // Vetur
  "vetur.format.options.tabSize": 2,
  "vetur.format.enable": true,
  "todo-tree.tree.showScanModeButton": false,

  // jsx snippet
  "editor.snippetSuggestions": "top",

  // markdownlint
  "markdownlint.ignore": ["node_modules/**/*.md"],
  "markdownlint.config": {
    "default": true,
    "MD029": { "ol-prefix": "ordered" }
  }
}
```
