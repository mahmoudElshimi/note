# Note - Simple Unix CLI Note Manager with [Encryption]

A lightweight, pass-inspired note management system with optional GPG encryption.

## Features
- Dual storage modes: Plain text or encrypted
- Hierarchical note organization
- Multi-line note support
- Clipboard integration with auto-clear
- Built-in search functionality
- Git version control integration
- QR code generation for sharing

## Installation

```bash
git clone https://github.com/mahmoudElshimi/note.git
chmod +x note/note
cp note/note /to/your/path/
```


### Dependencies
```bash
# Arch Linux
sudo pacman -S  bash  gnupg  tree git shred wipe

# Debian/Ubuntu
sudo apt install tree gpg xclip git shred wipe

# RHEL/CentOS
sudo yum install tree gnupg xclip git shred wipe
```

## Basic Usage

### Store Structure
Notes are stored in:
```
~/.note-store/
├── work/
│   ├── project1
│   └── meeting_notes.gpg
└── personal/
    └── ideas
```

### Core Commands
```bash
# Create note
note add work/project_ideas

# Edit note
note edit work/project_ideas

# View note
note show work/project_ideas

# List notes
note ls

# Search notes
note find project

# Search content
note grep "important"

# Delete note
note rm old/note
```

## Encryption

### Create Encrypted Note
```bash
note add -e secrets/api_keys
```

### Edit Encrypted Note
```bash
note edit -e secrets/api_keys
```

## Configuration

### Environment Variables
Add to ~/.bashrc or ~/.zshrc:
```bash
# Change storage location
export NOTE_STORE_DIR="$HOME/my-notes"

# Set preferred editor
export EDITOR="vim"

# Clipboard timeout (seconds)
export NOTE_CLIP_TIME=30
```

### Git Integration
```bash
# Initialize version control
note git init

# View history
note git log
```

## Advanced Usage

### Clipboard Operations
```bash
# Copy to clipboard
note show -c work/meeting_notes

# Generate QR code
note show -q contact_info
```

### Bulk Operations
```bash
# Find all TODOs
note grep "TODO"

# Backup notes
cp -r ~/.note-store ~/note-backup
```

## Troubleshooting

### GPG Errors
```bash
gpg --generate-key
```

### Clipboard Issues
```bash
# X11
install xclip

# Wayland
install wl-clipboard
```

## notemenu - Quick Note Selection Interface

### Description
A dmenu-based interface for quickly finding and accessing notes from your terminal or window manager.

### Features
- Fuzzy-find notes with dmenu/rofi
- Supports both X11 and Wayland
- Two interaction modes:
  - Copy to clipboard (default)
  - Direct typing into focused window (`--type` flag)
- Shows full note paths (e.g., "work/projects/backend")
- Works with both encrypted (.gpg) and plain text notes

### Installation
```bash
chmod +x notemenu
sudo cp notemenu /path/to/ur/path
```

## License
MIT/X License © 2025 mahmoudElShimi <mahmoudelshimi@protonmail.ch>


