# 🧠 **all_commands.md**
*A living Linux handbook + learning journal*

---

## 🗂️ Table of Contents
- [Core Navigation](#core-navigation)
- [File & Directory Management](#file--directory-management)
- [Permissions & Ownership](#permissions--ownership)
- [Package Management](#package-management)
- [Process & System Monitoring](#process--system-monitoring)
- [Networking & SSH](#networking--ssh)
- [Disk & Filesystem Management](#disk--filesystem-management)
- [Text Processing & Pipelines](#text-processing--pipelines)
- [System Logs & Services](#system-logs--services)
- [Automation & Scheduling](#automation--scheduling)
- [Diagnostics & Utilities](#diagnostics--utilities)
- [Day-wise Learning Notes](#day-wise-learning-notes)

---

## 🧭 Core Navigation
| Command | Description | Example | Output / Note |
|----------|--------------|----------|----------------|
| `pwd` | Show current working directory | `pwd` | `/home/nk` |
| `ls` | List contents of a directory | `ls -la` | Lists hidden files, permissions, owners |
| `cd` | Change directory | `cd ~/Documents` | Move to another directory |
| `tree` | Display directory structure as tree | `tree ~/lab` | Requires `sudo apt install tree` |
| `clear` | Clear the terminal screen | `clear` | Same as `Ctrl + L` |

---

## 📁 File & Directory Management
| Command | Description | Example | Output / Note |
|----------|--------------|----------|----------------|
| `mkdir` | Create a new directory | `mkdir projects` | Creates a folder named “projects” |
| `rmdir` | Remove empty directory | `rmdir old_folder` | Only works if empty |
| `touch` | Create empty file or update timestamp | `touch file.txt` | Creates or updates file |
| `cp` | Copy files/directories | `cp file1.txt backup.txt` | Use `-r` for directories |
| `mv` | Move or rename files/directories | `mv old.txt new.txt` | Works as rename |
| `rm` | Remove files/directories | `rm file.txt` | Use `-r` to remove folder |
| `cat` | View file content | `cat file.txt` | Prints to screen |
| `less` | View file interactively | `less file.txt` | Scroll with arrows, quit `q` |
| `head` | Show first N lines | `head -n 5 file.txt` | Default is 10 lines |
| `tail` | Show last N lines | `tail -f log.txt` | `-f` follows changes live |
| `find` | Search for files/directories | `find ~ -name '*.txt'` | Recursively searches |
| `locate` | Quickly find file by name | `locate file.txt` | Requires updated database (`sudo updatedb`) |
| `file` | Detect file type | `file image.jpg` | Shows MIME type or text info |

---

## 🔐 Permissions & Ownership
| Command | Description | Example | Output / Note |
|----------|--------------|----------|----------------|
| `whoami` | Show current user | `whoami` | Example: `nk` |
| `id` | Show user ID and groups | `id nk` | Includes UID/GID |
| `groups` | Show user’s groups | `groups` | Shows sudo/admin membership |
| `chmod` | Change permissions | `chmod 755 script.sh` | Owner rwx, others r-x |
| `chown` | Change ownership | `sudo chown nk:nk file.txt` | Owner/group set |
| `umask` | Default file permissions mask | `umask` | Adjusts new file perms |
| `sudo` | Run command as superuser | `sudo apt update` | Prompts for password |

---

## 📦 Package Management
| Command | Description | Example | Output / Note |
|----------|--------------|----------|----------------|
| `apt update` | Refresh package lists | `sudo apt update` | Fetches latest metadata |
| `apt upgrade` | Upgrade all packages | `sudo apt upgrade -y` | Installs new versions |
| `apt install` | Install new package | `sudo apt install htop` | Adds a program |
| `apt remove` | Remove package | `sudo apt remove nano` | Keeps config files |
| `apt purge` | Remove + configs | `sudo apt purge nano` | Cleans completely |
| `apt autoremove` | Remove unused deps | `sudo apt autoremove` | Cleans old packages |
| `apt show` | Display package info | `apt show git` | Includes version, dependencies |
| `dpkg -l` | List installed packages | `dpkg -l | grep vim` | Shows version |
| `snap install` | Install snap app | `sudo snap install code --classic` | For snap ecosystem |

---

## ⚙️ Process & System Monitoring
| Command | Description | Example | Output / Note |
|----------|--------------|----------|----------------|
| `ps aux` | Show all running processes | `ps aux | grep ssh` | Lists PID, user, etc. |
| `top` | Interactive process viewer | `top` | Realtime usage |
| `htop` | Enhanced `top` | `htop` | Use arrows, F10 to quit |
| `kill` | Terminate process | `kill 1234` | Sends SIGTERM |
| `killall` | Kill by name | `killall firefox` | Stops all firefox |
| `systemctl` | Manage system services | `systemctl status cron` | Show service state |
| `journalctl` | View system logs | `journalctl -xe` | Useful for debugging |
| `uptime` | Show uptime & load | `uptime` | Displays load avg |
| `free -h` | Show memory usage | `free -h` | Human-readable |
| `df -h` | Disk usage by filesystem | `df -h` | Mounted volumes |
| `du -sh *` | Size of folders/files | `du -sh ~/* | sort -h` | Summaries |

---

## 🌐 Networking & SSH
| Command | Description | Example | Output / Note |
|----------|--------------|----------|----------------|
| `ip a` | Show IP addresses | `ip a` | Interfaces & addresses |
| `ip route` | Show routing table | `ip route` | Gateway info |
| `ping` | Test connectivity | `ping -c 4 8.8.8.8` | Packet loss summary |
| `ss -tuln` | Show open ports | `ss -tuln` | Useful for checking services |
| `ufw status` | Firewall status | `sudo ufw status verbose` | Shows allowed ports |
| `ssh` | Remote login | `ssh user@host` | Secure shell connection |
| `scp` | Copy over SSH | `scp file.txt user@host:/tmp` | Secure file transfer |
| `ssh-keygen` | Generate SSH keys | `ssh-keygen -t ed25519` | Creates key pair |
| `ssh-copy-id` | Copy SSH key to host | `ssh-copy-id user@host` | Enables passwordless login |

---

## 💾 Disk & Filesystem Management
| Command | Description | Example | Output / Note |
|----------|--------------|----------|----------------|
| `lsblk` | List block devices | `lsblk` | Shows partitions |
| `blkid` | Display UUID of disks | `blkid` | Useful for fstab |
| `mount` | Mount a filesystem | `sudo mount /dev/sdb1 /mnt` | Attaches drive |
| `umount` | Unmount a filesystem | `sudo umount /mnt` | Detaches drive |
| `df -h` | Show free space | `df -h` | Disk usage overview |
| `du -h` | Folder size summary | `du -h --max-depth=1` | Space per dir |
| `fdisk` | Partition tool (MBR) | `sudo fdisk /dev/sdb` | Interactive utility |
| `ls -lh` | Human-readable listing | `ls -lh` | Sizes in KB/MB/GB |
| `mkfs.ext4` | Create filesystem | `sudo mkfs.ext4 /dev/sdb1` | Formats drive |

---

## 🧾 Text Processing & Pipelines
| Command | Description | Example | Output / Note |
|----------|--------------|----------|----------------|
| `echo` | Print text | `echo "Hello World"` | Output to stdout |
| `grep` | Search patterns | `grep "error" log.txt` | Matches lines |
| `awk` | Field-based text processing | `awk '{print $1}' file.txt` | Prints first column |
| `sed` | Stream editor (replace) | `sed 's/foo/bar/g' file.txt` | Replace all |
| `cut` | Extract columns | `cut -d':' -f1 /etc/passwd` | Get usernames |
| `sort` | Sort lines | `sort file.txt` | Alphabetical |
| `uniq` | Remove duplicates | `uniq -c names.txt` | Count unique lines |
| `wc` | Count words, lines | `wc -l file.txt` | Line count |
| `tee` | Output + save to file | `ls | tee files.txt` | Duplicates output |
| `xargs` | Build commands | `ls | xargs rm` | Executes commands per line |

---

## 🧩 System Logs & Services
| Command | Description | Example | Output / Note |
|----------|--------------|----------|----------------|
| `dmesg` | Kernel messages | `dmesg | tail` | Useful for debugging hardware |
| `journalctl` | Systemd logs | `journalctl -xe` | View service errors |
| `service` | Manage SysV services | `sudo service apache2 restart` | Start/stop/restart |
| `systemctl` | Manage systemd units | `systemctl list-units --type=service` | All active services |
| `last` | Show login history | `last` | Login/logout info |
| `who` | Show logged users | `who` | Terminal sessions |
| `uptime` | Show system uptime | `uptime` | With load averages |

---

## ⏱️ Automation & Scheduling
| Command | Description | Example | Output / Note |
|----------|--------------|----------|----------------|
| `crontab -e` | Edit cron jobs | `*/5 * * * * /path/script.sh` | Run script every 5 mins |
| `at` | Schedule one-time tasks | `echo "reboot" | at 2am` | Run once |
| `sleep` | Delay execution | `sleep 5` | Wait 5 seconds |
| `watch` | Run repeatedly | `watch -n 2 df -h` | Refresh every 2s |

---

## 🔍 Diagnostics & Utilities
| Command | Description | Example | Output / Note |
|----------|--------------|----------|----------------|
| `uname -a` | System info | `uname -a` | Kernel version |
| `lsb_release -a` | OS release info | `lsb_release -a` | Ubuntu version |
| `hostnamectl` | Host details | `hostnamectl` | Machine info |
| `lscpu` | CPU info | `lscpu` | Core/thread count |
| `lspci` | PCI devices | `lspci` | Hardware components |
| `lsusb` | USB devices | `lsusb` | USB hardware |
| `dmidecode` | BIOS info | `sudo dmidecode -t system` | System manufacturer |
| `history` | Command history | `history | tail` | Review past commands |

---

## 📘 Day-wise Learning Notes
### 🗓️ Day 1: Basic Navigation
- Practiced `pwd`, `cd`, `ls`, `mkdir`, `touch`
- Explored hidden files and directory paths
- Created sample folders in `~/lab/day1`

### 🗓️ Day 2: File Management
- Copied, moved, and deleted sample files
- Used `cat`, `less`, `head`, and `tail` to inspect data
- Learned `find` vs `locate`

*(Add daily logs as you progress!)*

---

### 🔗 Useful Links
- [GNU Coreutils Manual](https://www.gnu.org/software/coreutils/manual/coreutils.html)
- [Linux Command Library](https://linuxcommandlibrary.com/)
- [ExplainShell](https://explainshell.com/)
- [Ubuntu Manpages](https://manpages.ubuntu.com/)
- [OverTheWire Linux Wargames](https://overthewire.org/wargames/bandit/)

---
