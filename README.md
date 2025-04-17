# 🗂️ `ranger` — Terminal File Manager with Vim-like Keybindings

`ranger` is a lightweight and powerful command-line file manager that provides a minimal, curses-based interface with a multi-pane view and keybindings inspired by Vim.

---

## ✅ Features

- Multi-column view (like Midnight Commander or `mc`)  
- Vim-like keybindings for navigation  
- Preview of images, PDFs, and text files  
- Customizable with Python-based extensions  
- File operations: copy, move, delete, rename  
- Built-in file opener (integrates with `$EDITOR`, `$PAGER`)  
- Tabs, bookmarks, and history  

---

## 🔧 Installation

### On Debian/Ubuntu:
```bash
sudo apt update && sudo apt install ranger
```

### On Arch Linux:
```bash
sudo pacman -S ranger
```

### On macOS (via Homebrew):
```bash
brew install ranger
```

---

## 🚀 Basic Usage

### Start ranger:
```bash
ranger
```

### Open a directory directly:
```bash
ranger /path/to/folder
```

### Open a file with default app:
Press `Enter` on the file or use:
```bash
ranger --choosefile=/tmp/filename
```

---

## ⌨️ Essential Keybindings

| Key        | Action                         |
|------------|--------------------------------|
| `j` / `k`  | Move down/up                   |
| `h` / `l`  | Go back / enter directory      |
| `gg` / `G` | Jump to top / bottom           |
| `q`        | Quit                           |
| `yy`       | Yank (copy path)               |
| `dd`       | Delete file/folder             |
| `pp`       | Paste                          |
| `:delete`  | Delete with confirmation       |
| `:rename`  | Rename a file                  |
| `/`        | Search                         |
| `Tab`      | Switch tabs                    |
| `zh`       | Toggle hidden files            |

---

## 🧰 Configuration

### Initialize config:
```bash
ranger --copy-config=all
```
This creates config files in `~/.config/ranger/`, including:
- `rc.conf` — main keybindings and behavior
- `scope.sh` — preview script (media, PDFs, etc.)
- `rifle.conf` — file opener configuration

### Customize the opener (`rifle.conf`):
```bash
nano ~/.config/ranger/rifle.conf
```

### Example: open images with `feh`:
```
mime ^image, has feh, X, flag f = feh --scale-down --auto-zoom -- "%s"
```

---

## 🖼️ File Preview Support

To enable previews:
- Ensure `scope.sh` is executable  
- Install required tools:
  - `bat` or `highlight` (for syntax highlighting)
  - `pdftotext` / `poppler-utils`
  - `mediainfo` / `ffmpegthumbnailer`
  - `ueberzug` or `w3m` (for image previews in terminal)

---

## 🎯 Advanced Tips

- Use `:bulkrename` to rename multiple files with your `$EDITOR`  
- Set bookmarks using `m[a-z]` and jump with `'[a-z]`  
- Jump to last used directory: `cd $(ranger --choosedir=/tmp/dir); cd "$(cat /tmp/dir)"`  
- Launch with a chosen file:  
  ```bash
  ranger --choosefile=/tmp/file; cat /tmp/file
  ```

---

## 🧩 Alternatives

- `mc` — Midnight Commander  
- `lf` — Another minimalist file manager  
- `nnn` — Extremely fast and lightweight  

---

## 📚 More Info

- Website: [https://ranger.github.io](https://ranger.github.io)  
- GitHub: [https://github.com/ranger/ranger](https://github.com/ranger/ranger)  
- Man Page: `man ranger`  
- Help: `ranger --help`
