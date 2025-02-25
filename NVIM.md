# Neovim VS Code Cheat Sheet
- [Neovim VS Code Cheat Sheet](#neovim-vs-code-cheat-sheet)
  - [**1. Insert Mode Commands**](#1-insert-mode-commands)
  - [**2. Navigation**](#2-navigation)
  - [**3. Editing Commands**](#3-editing-commands)
  - [**4. Visual Mode Commands**](#4-visual-mode-commands)
  - [**5. Searching \& Replacing**](#5-searching--replacing)
  - [**6. Working with Buffers (Files)**](#6-working-with-buffers-files)
  - [**7. Splits \& Windows**](#7-splits--windows)
  - [**8. VS Code-Specific Neovim Commands**](#8-vs-code-specific-neovim-commands)
  - [**9. Registers (Clipboard \& Copy-Paste)**](#9-registers-clipboard--copy-paste)
  - [**10. Macros**](#10-macros)

A quick reference guide for using Neovim inside VS Code, ordered by the most frequently used commands.

---

## **1. Insert Mode Commands**
| Command | Description |
|---------|-------------|
| `i` | Enter **Insert mode** before the cursor. |
| `a` | Enter **Insert mode** after the cursor. |
| `o` | Insert a new line **below** and enter Insert mode. |
| `O` | Insert a new line **above** and enter Insert mode. |
| `Esc` | Exit Insert mode and return to Normal mode. |

---

## **2. Navigation**
| Command | Description |
|---------|-------------|
| `h` | Move left by one character. |
| `l` | Move right by one character. |
| `j` | Move down by one line. |
| `k` | Move up by one line. |
| `w` | Jump forward to the start of the next word. |
| `b` | Jump backward to the start of the previous word. |
| `0` | Move to the beginning of the current line. |
| `^` | Move to the first non-blank character of the line. |
| `$` | Move to the end of the current line. |
| `gg` | Move to the start of the file. |
| `G` | Move to the end of the file. |
| `Ctrl-d` | Scroll half a page down. |
| `Ctrl-u` | Scroll half a page up. |

---

## **3. Editing Commands**
| Command | Description |
|---------|-------------|
| `x` | Delete the character under the cursor. |
| `dd` | Delete the entire line. |
| `D` | Delete everything from the cursor to the end of the line. |
| `yy` | Copy (yank) the current line. |
| `p` | Paste the copied text **after** the cursor. |
| `P` | Paste the copied text **before** the cursor. |
| `r<char>` | Replace a character under the cursor with `<char>`. |
| `J` | Join the current line with the next one. |
| `u` | Undo the last action. |
| `Ctrl-r` | Redo the last undone action. |

---

## **4. Visual Mode Commands**
| Command | Description |
|---------|-------------|
| `v` | Start **Visual mode** (select text by moving cursor). |
| `V` | Start **Visual Line mode** (select entire lines). |
| `Ctrl-v` | Start **Visual Block mode** (column selection). |
| `y` | Yank (copy) the selected text. |
| `d` | Delete the selected text. |
| `>` | Indent the selected text right. |
| `<` | Indent the selected text left. |

---

## **5. Searching & Replacing**
| Command | Description |
|---------|-------------|
| `/text` | Search for **text** in the file. |
| `?text` | Search **backwards** for **text**. |
| `n` | Move to the **next** search match. |
| `N` | Move to the **previous** search match. |
| `:%s/old/new/g` | Replace **old** with **new** globally in the file. |
| `:%s/old/new/gc` | Replace **old** with **new**, confirming each replacement. |

---

## **6. Working with Buffers (Files)**
| Command | Description |
|---------|-------------|
| `:e filename` | Open **filename** in a new buffer. |
| `:w` | Save (write) the current file. |
| `:q` | Quit if no unsaved changes. |
| `:q!` | Quit **without saving** changes. |
| `:wq` or `ZZ` | Save and quit. |
| `:bn` | Go to the **next** buffer. |
| `:bp` | Go to the **previous** buffer. |
| `:bd` | Close the current buffer. |
| `:ls` | List all open buffers. |

---

## **7. Splits & Windows**
| Command | Description |
|---------|-------------|
| `:split filename` | Open **filename** in a **horizontal split**. |
| `:vsplit filename` | Open **filename** in a **vertical split**. |
| `Ctrl-w h` | Move to the **left** window. |
| `Ctrl-w l` | Move to the **right** window. |
| `Ctrl-w j` | Move to the **bottom** window. |
| `Ctrl-w k` | Move to the **top** window. |
| `Ctrl-w q` | Close the current window. |

---

## **8. VS Code-Specific Neovim Commands**
| Command | Description |
|---------|-------------|
| `:VscodeNotify vscode-neovim.ctrl+n` | Open VS Code file explorer. |
| `:VscodeNotify vscode-neovim.workbench.action.toggleSidebarVisibility` | Toggle sidebar visibility. |
| `:VscodeNotify vscode-neovim.workbench.action.togglePanel` | Toggle bottom panel. |
| `:VscodeNotify vscode-neovim.workbench.action.quickOpen` | Open quick file search. |
| `:VscodeNotify vscode-neovim.workbench.action.showCommands` | Show command palette. |

---

## **9. Registers (Clipboard & Copy-Paste)**
| Command | Description |
|---------|-------------|
| `"+y` | Copy to system clipboard. |
| `"+p` | Paste from system clipboard. |
| `"0p` | Paste the last yanked text. |
| `"_d` | Delete without saving to a register. |

---

## **10. Macros**
| Command | Description |
|---------|-------------|
| `qa` | Start recording a macro in register `a`. |
| `q` | Stop recording. |
| `@a` | Play back the macro stored in `a`. |
| `@@` | Repeat the last macro. |

---

This cheat sheet covers the most frequently used Neovim commands inside VS Code. Happy coding! 🚀
