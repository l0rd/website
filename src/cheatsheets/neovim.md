---
title: Neovim cheatsheet - lorie.do
layout: "base.njk"
pageClass: cheatsheet
---

# NEOVIM

<p class="intro">Shortcuts from <a href="https://github.com/l0rd/kickstart.nvim">my Neovim config</a>, based on <a href="https://github.com/nvim-lua/kickstart.nvim">kickstart.nvim</a>. <code>&lt;leader&gt;</code> is <code>Space</code>.</p>

## Debugging (Go)

| Keys / command | Action |
|----------------|--------|
| `<leader>b` | Toggle breakpoint |
| `<leader>B` | Conditional breakpoint |
| `F5` | Start debugging / continue |
| `F1` / `F2` / `F3` | Step into / over / out |
| `F7` | Reopen the debug panels (e.g. to see output after the program exits) |
| `:lua require('dap').set_log_level('TRACE')` then `:DapShowLog` | Troubleshoot the debugger |

## Completion and snippets

| Keys | Action |
|------|--------|
| `Ctrl+Space` | Open completion menu (again: show docs) |
| `Ctrl+n` / `Ctrl+p` | Next / previous suggestion |
| `Ctrl+y` | Accept suggestion |
| `Ctrl+e` | Close menu |
| `Tab` / `Shift+Tab` | Jump between snippet placeholders |
| `Ctrl+k` | Toggle signature help |
| `for` `forr` `if` `ife` `ir` | Go snippets: loop, range loop, if, if/else, `if err != nil` |

## Git diffs

| Keys / command | Action |
|----------------|--------|
| `]c` / `[c` | Next / previous change |
| `<leader>hp` | Preview change in a popup |
| `<leader>hi` | Preview change inline |
| `<leader>hd` / `<leader>hD` | Side-by-side diff vs staged / last commit |
| `<leader>tw` | Toggle word-level diff highlighting |
| `<leader>hs` / `<leader>hr` | Stage / undo change (selected lines in visual mode) |
| `<leader>lg` | Open lazygit |
| `:Git`, then `=` or `dv` on a file | Fugitive status: inline / side-by-side diff |
| `gb` | Open the current line on GitHub |

## Yank and paste

| Keys / command | Action |
|----------------|--------|
| `:reg` or `:Telescope registers` | Show registers |
| `"0p` | Paste last yank (even after deleting) |
| `"1p` … `"9p` | Paste recent line deletes |
| `"+p` | Paste system clipboard |
| `"ayy` / `"Ayy` / `"ap` | Yank to / append to / paste from register `a` |

## Buffers and files

| Keys / command | Action |
|----------------|--------|
| `Ctrl+^` | Switch to previous buffer |
| `:bp` / `:bn` | Previous / next buffer |
| `Ctrl+o` / `Ctrl+i` | Jump back / forward (across files) |
| `<leader><leader>` | Pick an open buffer |
| `:call delete(expand('%')) \| bdelete!` | Delete current file |
| `:GDelete` | Delete current file with `git rm` |
| `:Ex`, then `D` on a file | Delete from the file browser |

## Themes and plugins

| Keys / command | Action |
|----------------|--------|
| `<leader>tc` or `:Themery` | Theme picker (live preview, choice is saved) |
| `:lua vim.pack.update()` | Update plugins |
| `:Mason` | Manage language servers and tools |
