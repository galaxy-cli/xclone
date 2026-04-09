# CloudSync
A lightweight Bash wrapper for rclone that allows you to perform sync, copy, and maintenance tasks across multiple cloud remotes simultaneously.

## Features
- **Multi-Remote Support**: Target multiple clouds (e.g., Google Drive and Dropbox) with a single command.
- **Automatic Setup**: Checks for rclone and installs it if missing.
- **Safety First**: Includes a --dry-run mode to preview changes before they happen.
- **Smart Validation**: Prevents execution if required paths or remotes are missing.

## Installation
1. Save the script as cloudsync:
```
nano cloudsync
```
2. Make it executable:
```
chmod +x cloudsync
```
3. (Optional) Move it to your path for global access:
```
sudo mv cloudsync /usr/local/bin/
```

## Usage
```
cloudsync [ACTION] -c "remote1,remote2" [OPTIONS]
```

### Actions
- `--sync`: Mirror source to destination (Warning: Deletes extra files on remote to match source).
- `--copy`: Copy source to destination (keeps existing files on remote).
- `--remove`: Delete a specific file from specified remotes.
- `--remove-dir`: Delete an entire directory (purge) from specified remotes.
- `--make-dir`: Create a new directory on remotes.
- `-l, --list`: List contents of the remote path.

### Required Parameters
- `-c, --cloud`: Comma-separated list of your rclone remotes (e.g., "gdrive,mega").
- `-p, --path`: Local source path (required for --sync and --copy).
- `-d, --dest`: Remote destination path.

### Flags
- `-n, --dry-run`: Trial run without making changes.
- `-v, --verbose`: Print the exact rclone commands being executed.
- `-h, --help`: Display the help menu.

## Examples
1. Sync a local folder to two clouds simultaneously:
```
cloudsync --sync -c "mega,gdrive" -p ~/Documents -d "Backup/Documents"
```
2. Safely preview a directory deletion:
```
cloudsync --remove-dir -n -c "dropbox" -d "OldBackups"
```
3. List files on a specific remote path:
```
cloudsync --list -c "gdrive" -d "Photos/2023"
```
## Important Note
This script relies on rclone. Ensure you have already configured your remotes using rclone config before using this wrapper.