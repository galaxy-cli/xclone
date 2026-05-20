# xclone

`xclone` is a lightweight, high-utility multi-remote wrapper that scales native `rclone` cloud storage operations seamlessly across multiple backends simultaneously.

## Features

* **Multi-Remote Scaling**: Execute cloud actions across comma-separated endpoints (e.g., `mega,gdrive,dropbox`) in a single command pass.
* **Intelligent Parameter Fallbacks**: Omit target destination folders on single-path operations to automatically reference the root profile directory (`/`).
* **Unquoted Flexibility**: Accepts simple unquoted remote configurations and target names cleanly without shell breaking hazards.
* **Integrated Environments**: Access native profile configuration menus and connection listing matrices inside the unified wrapper interface.

---

## Installation

### Prerequisites
Ensure that `rclone` is installed and available inside your system path environment:
```bash
# Ubuntu / Debian systems
sudo apt install rclone

# macOS platforms
brew install rclone
```

### Script Setup
1. Clone your project repository or copy the code file down directly to your engine.
2. Mark the local file script asset as executable:
```bash
chmod +x xclone
```

3. (Optional) Move the file into your local path bin allocation profile space to unlock global operational context execution matching:
```bash
sudo mv xclone /usr/local/bin/xclone
```

---

## Usage Reference

```text
======================================================================
 xclone v2.5.0 - Multi-Remote Rclone Wrapper
======================================================================
Usage: xclone [OPTIONS] ACTION REMOTES [PATH1] [PATH2]
       xclone listremotes | config

Options:
  -n, --dry-run     Simulate command execution without changing files
  -v, --verbose     Print underlying live rclone system calls
  -h, --help        Show this reference screen

Actions:
  Dual-Path         sync, copy, move, check
  Single-Path       lsf, ls, size, mkdir, purge, deletefile
======================================================================
```

---

## Action Profiles & Examples

### 1. Account Systems Architecture & Setup
Launch the configuration manager tool or review currently configured profile endpoints directly:
```bash
xclone config
xclone listremotes
```

### 2. Single-Path Directory Audits & Inspection Tasks
Query file trees or directory structures. Omitting paths targets root folders directly:
```bash
# List top level profiles fast
xclone lsf mega

# Recursively crawl nested assets inside specific folders
xclone ls gdrive Backups/Documents

# Evaluate total scale and data metrics instantly
xclone size dropbox Media/Archive
```

### 3. Dual-Path Synchronization & Content Deployment
Push local files out into remote storage destinations safely:
```bash
# Copy local development components up into secondary networks safely
xclone copy mega,dropbox ~/Projects SourceArchive

# Sync files across backends exactly (Warning: Matches target identically!)
xclone sync gdrive ~/Documents PersonalVault
```

### 4. Simulation & Diagnostic Safe Mode Verification
Verify syntax structural parameters and track exact raw underlying `rclone` system terminal hooks without executing destructive actions:
```bash
xclone -nv sync mega,gdrive ~/Desktop ProductionDeploy
```

---          