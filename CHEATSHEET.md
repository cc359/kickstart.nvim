# Neovim Keymap Cheatsheet

Generated from my `init.lua` + kickstart plugins. Snapshot as of Feb 2026 —
update it when you add mappings. **Leader key = `Space`**

## How to discover keys (the most important shortcuts!)

| Key | Action |
|---|---|
| `Space` (then wait) | which-key popup — shows all groups and keys |
| `Space s k` | Fuzzy-search **all** keymaps with Telescope |
| `:help <key>` | Docs for any key, e.g. `:help CTRL-W_s` |

## General

| Key | Action |
|---|---|
| `Esc` | Clear search highlighting |
| `[d` / `]d` | Previous / next diagnostic |
| `Space e` | Show diagnostic error popup |
| `Space q` | Open diagnostic quickfix list |
| `Ctrl-h/j/k/l` | Move to split — or **tmux pane** if no split that way |
| `Esc Esc` | Exit terminal mode back to normal mode |

## Search (Telescope) — `Space s`

| Key | Action |
|---|---|
| `Space /` | Fuzzy search in **current buffer** |
| `Space s f` | Find files |
| `Space Space` | Find open buffers |
| `Space s g` | Live grep (whole project) |
| `Space s w` | Grep for word under cursor |
| `Space s /` | Live grep in open files only |
| `Space s d` | Search diagnostics |
| `Space s r` | Resume last Telescope search |
| `Space s .` | Recent files |
| `Space s h` | Search `:help` |
| `Space s k` | Search keymaps |
| `Space s s` | All Telescope builtins |
| `Space s n` | Search my Neovim config files |

In Telescope: `Ctrl-n/p` next/prev, `Enter` open, `Esc` cancel, `Ctrl-u/d` scroll preview.

## Code / LSP — works on cursor word

| Key | Action |
|---|---|
| `gd` | **G**o to **d**efinition (`Ctrl-t` to jump back) |
| `gr` | Find **r**eferences |
| `gI` | Go to **i**mplementation |
| `gD` | Go to **d**eclaration |
| `K` | Hover documentation |
| `Space D` | Type definition |
| `Space r n` | Re**n**ame symbol (project-wide) |
| `Space c a` | **C**ode **a**ction (quick fixes, imports) |
| `Space d s` | Document symbols |
| `Space w s` | Workspace symbols |

## Autocomplete (insert mode — nvim-cmp)

| Key | Action |
|---|---|
| `Ctrl-n` / `Ctrl-p` | Next / previous completion item |
| `Ctrl-y` | Accept completion (auto-imports too) |
| `Ctrl-Space` | Manually trigger completions |
| `Ctrl-b` / `Ctrl-f` | Scroll completion doc window |
| `Ctrl-l` / `Ctrl-h` | Jump forward / back through snippet placeholders |
| `Tab` / `Shift-Tab` | Also jump snippets (when a snippet is active) |
| `Ctrl-s` | Function signature help |

## Debug (nvim-dap)

| Key | Action |
|---|---|
| `F5` | Start / continue debugging |
| `F1` / `F2` / `F3` | Step into / over / out |
| `F7` | Toggle debug UI |
| `Space b` | Toggle breakpoint |
| `Space B` | Breakpoint with condition |

## Go (go.nvim)

| Key | Action |
|---|---|
| `Space g r` | Run current file |
| `Space g t` | Test function under cursor |
| `Space g T` | Test whole package |
| `Space g a` | Alternate between impl and test file |

## Comments (Comment.nvim)

| Key | Action |
|---|---|
| `gcc` | Toggle comment on current line |
| `gc` | Toggle comment on selection (visual) or motion (`gc3j`, `gcaw`) |

## Surroundings (mini.surround)

| Key | Action |
|---|---|
| `s a i w )` | **S**urround **a**dd: `word` → `(word)` (any textobj/selection) |
| `s d '` | **D**elete surrounding quotes |
| `s r ) ]` | **R**eplace `(...)` with `[...]` |

## Text objects (mini.ai — use with any operator: `v`, `d`, `c`, `y`...)

| Key | Action |
|---|---|
| `va)` | Visually select around parens |
| `ci'` | Change inside quotes |
| `vinq` | Select inside next quote |
| Works with `(`, `[`, `{`, `'`, `"`, backtick, function calls `f`, args `a`, etc. |

## Automatic (no keys needed)

- **LSP** (gopls, ts_ls, lua_ls, html, css...) attaches per filetype — `:LspInfo` to check
- **Format on save**: Go → `goimports`+`gofumpt`; Lua → `stylua`; web → `prettierd`
- **Lint**: `eslint_d` (JS/TS), `markdownlint` — shown as diagnostics, `]d`/`[d` to hop
- **HTML/JSX tags** auto-close via nvim-ts-autotag (tags only, not brackets)
