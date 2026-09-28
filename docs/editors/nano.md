# Nano Cheatsheet 📝

A quick reference guide for essential command-line editing operations in GNU Nano.

---

## 1. File Operations & Navigation

| Shortcut | Description |
| :--- | :--- |
| `nano <filename>` | Open or create a file in Nano |
| `nano +<line_number> <file>` | Open file and jump directly to a specific line number |
| `nano -v <filename>` | Open file in view-only (read-only) mode |
| `Ctrl + O` | Write out (Save changes to disk) |
| `Ctrl + X` | Exit Nano (prompts to save if modified) |
| `Ctrl + R` | Insert another file into the current document |

---

## 2. Cursor Movement

| Shortcut | Description |
| :--- | :--- |
| `Ctrl + A` | Move cursor to the beginning of the current line |
| `Ctrl + E` | Move cursor to the end of the current line |
| `Ctrl + Y` / `Ctrl + V` | Page Up / Page Down |
| `Ctrl + _` | Jump to a specific line and column number |
| `Alt + \` | Jump to the beginning of the file |
| `Alt + /` | Jump to the end of the file |

---

## 3. Editing, Cutting & Pasting

| Shortcut | Description |
| :--- | :--- |
| `Ctrl + K` | Cut current line (or selected text) to the kill-buffer |
| `Ctrl + U` | Uncut (Paste) contents from the kill-buffer |
| `Alt + 6` | Copy current line (or selected text) to the kill-buffer |
| `Alt + A` | Set/unset mark for selecting text block |
| `Alt + Del` | Delete word to the left |
| `Ctrl + D` | Delete character under the cursor |

---

## 4. Search & Replace

| Shortcut | Description |
| :--- | :--- |
| `Ctrl + W` | Search for string or regular expression |
| `Alt + W` | Repeat the last search (Find next) |
| `Ctrl + \` | Search and replace text |
| `Alt + C` | Toggle case-sensitive search on/off |

---

## 5. View & Toggle Options

| Shortcut | Description |
| :--- | :--- |
| `Ctrl + C` | Show current line number, column, and file info |
| `Alt + N` | Toggle line numbers display |
| `Alt + $` | Toggle soft line wrapping |
| `Alt + X` | Toggle help mode at the bottom |
