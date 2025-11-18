# VSCodeVim Cheat Sheet 🎹

> Quick reference for moving fast inside code using Vim keybindings in VS Code (VSCodeVim).

---

## 🔤 Word-by-word movement

| Keys   | Description                          |
|--------|--------------------------------------|
| `w`    | Jump to **next word start**          |
| `e`    | Jump to **next word end**            |
| `b`    | Jump to **previous word start**      |
| `ge`   | Jump to **previous word end**        |
| `W`    | Jump to **next WORD** (space-based)  |
| `E`    | Jump to **next WORD end**            |
| `B`    | Jump to **previous WORD start**      |

---

## 📏 Line movement

| Keys | Description                                   |
|------|-----------------------------------------------|
| `0`  | Go to **start of line** (column 0)            |
| `^`  | Go to **first non-whitespace** character      |
| `$`  | Go to **end of line**                         |
| `gj` | Move **down one wrapped screen line**         |
| `gk` | Move **up one wrapped screen line**           |

---

## 🔍 In-line character jumps

| Keys       | Description                                         |
|------------|-----------------------------------------------------|
| `f{char}`  | Jump **to** next `{char}` on the line               |
| `t{char}`  | Jump **before** next `{char}` on the line           |
| `F{char}`  | Jump **backwards to** `{char}`                      |
| `T{char}`  | Jump **backwards before** `{char}`                  |
| `;`        | Repeat last `f` / `t` / `F` / `T` motion            |
| `,`        | Repeat last `f` / `t` / `F` / `T` in opposite direction |

---

## 📦 Blocks / paragraphs / scopes

| Keys | Description                                                  |
|------|--------------------------------------------------------------|
| `{`  | Jump to **previous block/paragraph** (previous empty line)   |
| `}`  | Jump to **next block/paragraph**                             |
| `%`  | Jump between **matching** `()`, `{}`, `[]`                   |

Use `%` on a brace/paren to jump between scope boundaries.

---

## 📜 Screen & file movement

| Keys        | Description                     |
|-------------|---------------------------------|
| `<C-d>`     | Half page **down**              |
| `<C-u>`     | Half page **up**                |
| `<C-f>`     | Full page **forward**           |
| `<C-b>`     | Full page **backward**          |
| `gg`        | Go to **top** of file           |
| `G`         | Go to **bottom** of file        |
| `{number}G` | Go to **line `{number}`**       |

---

## 🔎 Search-based navigation

| Keys            | Description                                |
|-----------------|--------------------------------------------|
| `/text` + `↵`   | Search **forward** for `text`              |
| `?text` + `↵`   | Search **backward** for `text`             |
| `n`             | Go to **next** search match                |
| `N`             | Go to **previous** search match            |
| `*`             | Search forward for **word under cursor**   |
| `#`             | Search backward for **word under cursor**  |

### 🚫 Clear search highlighting

| Command           | Description                     |
|-------------------|---------------------------------|
| `:noh` + `↵`      | Clear search highlighting       |
| `:nohlsearch` + `↵` | Same as above, full command |

---

## 🧠 Jump history

| Keys      | Description                                      |
|-----------|--------------------------------------------------|
| `<C-o>`   | Jump to **older** cursor position (go back)      |
| `<C-i>`   | Jump to **newer** cursor position (go forward)   |
| `` `` ``  | Jump to **last exact position** (toggle)         |

---

## 🪟 Moving between splits (editor groups)

Use `<C-w>` (Ctrl + w) followed by direction:

| Keys            | Description            |
|-----------------|------------------------|
| `<C-w> h`       | Focus split **left**   |
| `<C-w> l`       | Focus split **right**  |
| `<C-w> j`       | Focus split **down**   |
| `<C-w> k`       | Focus split **up**     |
| `<C-w> w`       | Go to **next** split   |
| `<C-w> p`       | Go to **previous** split |

---

## 🗂 Moving between tabs

| Keys        | Description                          |
|-------------|--------------------------------------|
| `gt`        | Go to **next tab**                   |
| `gT`        | Go to **previous tab**               |
| `{number}gt`| Go to tab **number `{number}`**      |

VS Code native (also usable):

| Shortcut              | Description       |
|-----------------------|-------------------|
| `Ctrl + Tab`          | Next tab          |
| `Ctrl + Shift + Tab`  | Previous tab      |

---

## 🗑 Deleting word-by-word & text objects

### Basic word deletes

| Keys  | Description                                        |
|-------|----------------------------------------------------|
| `dw`  | Delete from cursor → **start of next word**        |
| `de`  | Delete from cursor → **end of current word**       |
| `db`  | Delete from cursor → **start of previous word**    |
| `diw` | Delete **entire word under cursor** (“delete inner word”) |

### BIG WORD (space-separated) deletes

| Keys  | Description                                      |
|-------|--------------------------------------------------|
| `dW`  | Delete until **next WORD** (space-delimited)     |
| `dE`  | Delete until **end of current WORD**             |
| `dB`  | Delete back to **start of previous WORD**        |

### Line-based deletes

| Keys | Description                          |
|------|--------------------------------------|
| `d$` | Delete from cursor → **end of line** |
| `d0` | Delete from cursor → **start of line** |

### Structural deletes (text objects)

| Keys  | Description                                  |
|-------|----------------------------------------------|
| `di)` | Delete **inside parentheses** `( … )`        |
| `di]` | Delete **inside brackets** `[ … ]`           |
| `di}` | Delete **inside braces** `{ … }`             |
| `di"` | Delete **inside double quotes** `" … "`      |
| `di'` | Delete **inside single quotes** `' … '`      |

### Change (delete + insert) word

| Keys  | Description                                                |
|-------|------------------------------------------------------------|
| `ciw` | Change **inner word** (delete word and enter insert mode)  |
| `ce`  | Change from cursor → **end of word** and enter insert mode |

---

## 🧾 Minimal “always remember” set

- Words: `w`, `b`, `e`, `W`, `B`
- Lines: `0`, `^`, `$`
- Blocks/scopes: `{`, `}`, `%`
- File: `gg`, `G`, `<C-d>`, `<C-u>`
- Search: `/`, `n`, `N`, `*`, `#`
- Splits: `<C-w> h/j/k/l`
- Tabs: `gt`, `gT`
- Delete word: `dw`, `diw`, `ciw`

---

## 🔧 VS Code `settings.json` (with VSCodeVim)

Below is the current `settings.json` including Vim-related settings.  
Use this as your VS Code settings file.

```jsonc
{
  "files.autoSave": "afterDelay",
  "workbench.iconTheme": "material-icon-theme",
  "editor.fontFamily": "'JetBrains Mono', monospace",
  "editor.wordWrap": "on",
  "[typescript]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.formatOnSave": true,
  "git.confirmSync": false,
  "editor.fontSize": 13,
  "terminal.integrated.fontSize": 12,
  "terminal.integrated.lineHeight": 1.1,
  "terminal.integrated.letterSpacing": 0.5,
  "editor.tabSize": 2,
  "editor.cursorStyle": "block",
  "workbench.editor.enablePreview": false,
  "terminal.integrated.fontFamily": "JetBrains Mono",
  "editor.fontVariations": true,
  "workbench.fontAliasing": "antialiased",
  "editor.fontWeight": "100",
  "editor.letterSpacing": 0.5,
  "editor.lineHeight": 1.4,
  "editor.cursorBlinking": "smooth",
  "editor.fontLigatures": true,
  "workbench.colorTheme": "Default Dark Modern",
  "editor.accessibilitySupport": "off",

  // ===== Vim-like behaviour =====
  "vim.useSystemClipboard": true,              // yy / p use system clipboard
  "vim.hlsearch": true,                        // highlight search results
  "vim.incsearch": true,                       // show matches as you type / search
  "vim.ignorecase": true,                      // case-insensitive search...
  "vim.smartcase": true,                       // ...unless search has capitals
  "vim.cursorStylePerMode": true,              // different cursor normal/insert/visual
  "vim.mouseSelectionGoesIntoVisualMode": true,
  "vim.useCtrlKeys": true,
  "vim.handleKeys": {
    "<C-d>": true,
    "<C-u>": true,
    "<C-f>": true,
    "<C-b>": true,
    "<C-e>": true,
    "<C-y>": true,
    "<C-w>": true,
    "<C-n>": true,
    "<C-p>": true
  },

  // ===== Editor tweaks that feel Vimmy =====
  "editor.lineNumbers": "relative",            // like :set relativenumber
  "editor.minimap.enabled": false,             // no minimap in classic Vim
  "editor.scrollBeyondLastLine": false         // stop at EOF like Vim
}
