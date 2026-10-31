# Linux Administration & Automation Practice

A structured hands-on project to learn and practice core Linux system administration, networking, and automation. Built on Fedora Linux, this repository contains practical scripts and configurations for daily sysadmin tasks.

## 📂 Repository Structure

*   `configs/` - Configuration files and templates.
*   `logs/` - Directory for storing local system diagnostic reports.
*   `notes/` - Markdown files with command references and theory (e.g., `commands.md`).
*   `scripts/` - Executable Bash scripts for automation and diagnostics.

## 🚀 Key Modules Completed

### 1. System & File Management
*   Navigating the Linux filesystem (absolute and relative paths).
*   Managing file permissions and ownership (`chmod`, `chown`).
*   Process management and monitoring (`ps`, `grep`, `kill`).
*   Reading and filtering system logs (`journalctl`, `tail`).
*   Disk space management (`df`, `du`).

### 2. Networking & Security
*   Checking network interfaces and routing tables (`ip a`, `ip r`).
*   Testing external connectivity and DNS resolution (`ping`).
*   Monitoring active ports and listening sockets (`ss -tulpn`).
*   Verifying system firewall status (`firewalld`).

### 3. Bash Scripting & Automation
*   **`sysreport.sh`**: Generates a quick system health summary (current date, uptime, and root filesystem usage) and logs it for review.
*   **`backup.sh`**: Performs an automated, incremental backup of the project directory to a dedicated backup location using `rsync`.
*   **Systemd Integration**: Configured user-level `systemd` services and timers (`backup.service` and `backup.timer`) to automate the backup process hourly in the background.
*   **Shell Customization**: Created custom bash aliases (e.g., `syslog`) in `.bashrc` for streamlined log reading.

## 📝 Command Cheat Sheet

Here are the essential commands learned and used in this project:

**File & Directory Operations:**
*   `mkdir <dir>` - Create a new directory.
*   `mkdir -p <path>` - Create a directory and its parents if they don't exist.
*   `touch <file>` - Create an empty file.
*   `cp <source> <dest>` - Copy files.
*   `mv <source> <dest>` - Move or rename files/directories.
*   `rm <file>` - Remove a file.
*   `rm -r <dir>` - **Remove a directory and all its contents recursively.**
*   `rmdir <dir>` - Remove an *empty* directory.
*   `find . -name "<name>"` - Search for a file by name in the current directory.

**System & Process Monitoring:**
*   `df -h` - Show available disk space in human-readable format.
*   `du -sh <dir>` - Calculate the total size of a specific directory.
*   `ps -aux` - List all running processes.
*   `kill <PID>` - Terminate a process gracefully (use `-9` for force kill).

**Services & Logs (systemd):**
*   `systemctl status <service>` - Check if a system service is running.
*   `systemctl --user start <service>` - Start a user-level service.
*   `systemctl --user list-timers` - Show active scheduled tasks.
*   `journalctl -n 20` - Show the last 20 log entries.

## 🛠️ Usage

To run the system diagnostic script:
```bash
./scripts/sysreport.sh > logs/sysreport.txt
```

To trigger the backup script manually:
```bash
./scripts/backup.sh
```

## ⚙️ Requirements
*   Linux OS (Tested on Fedora)
*   `rsync` for incremental backups
*   `systemd` for task scheduling
