# LPIC-1 Exam Questions 101-110 (with Solutions)

Reference objective set: LPIC-1 Objectives V5.0
https://wiki.lpi.org/wiki/LPIC-1_Objectives_V5.0

## 1. TOPIC 101: System Architecture

### 101.1 Determine and configure hardware settings

1. **Q:** Which command lists PCI devices and their IDs?
   **A:** Use:
   ```bash
   lspci
   ```

2. **Q:** Where can you view current IRQ assignments?
   **A:** Check:
   ```text
   /proc/interrupts
   ```

3. **Q:** Which command loads a kernel module at runtime?
   **A:** Use:
   ```bash
   modprobe <module_name>
   ```

### 101.2 Boot the system

4. **Q:** What is the purpose of `initramfs` during boot?
   **A:** It provides a temporary root filesystem with drivers/tools needed to mount the real root filesystem.

5. **Q:** Which file usually contains default GRUB kernel options?
   **A:**
   ```text
   /etc/default/grub
   ```

6. **Q:** How do you inspect kernel parameters used in the current boot?
   **A:**
   ```bash
   cat /proc/cmdline
   ```

### 101.3 Boot targets, shutdown, reboot

7. **Q:** Which command shows the default `systemd` target?
   **A:**
   ```bash
   systemctl get-default
   ```

8. **Q:** How can you switch into rescue mode from a running system?
   **A:**
   ```bash
   systemctl isolate rescue.target
   ```

9. **Q:** Which target maps closest to classic runlevel 3?
   **A:**
   ```text
   multi-user.target
   ```

---

## 2. TOPIC 102: Linux Installation and Package Management

1. **Q:** Which command can create GPT partitions interactively?
   **A:**
   ```bash
   gdisk /dev/sdX
   ```

2. **Q:** Which file lists static filesystem mounts?
   **A:**
   ```text
   /etc/fstab
   ```

3. **Q:** On Debian/Ubuntu, which command rebuilds GRUB config?
   **A:**
   ```bash
   update-grub
   ```

4. **Q:** How do you refresh the shared library cache after library changes?
   **A:**
   ```bash
   ldconfig
   ```

5. **Q:** Which command installs a local Debian package file?
   **A:**
   ```bash
   dpkg -i package.deb
   ```

6. **Q:** Which command removes an RPM package?
   **A:**
   ```bash
   rpm -e package_name
   ```

7. **Q:** Which command shows virtualization capability from CPU flags?
   **A:**
   ```bash
   egrep '(vmx|svm)' /proc/cpuinfo
   ```

---

## 3. TOPIC 103: GNU and Unix Commands

1. **Q:** Which command shows the current working directory?
   **A:**
   ```bash
   pwd
   ```

2. **Q:** Which command joins lines from two files by common field?
   **A:**
   ```bash
   join file1 file2
   ```

3. **Q:** Which command archives files in tar format?
   **A:**
   ```bash
   tar -cvf archive.tar <files>
   ```

4. **Q:** How do you append stdout to a file?
   **A:**
   ```bash
   command >> output.log
   ```

5. **Q:** Which command sends SIGTERM to process ID 1234?
   **A:**
   ```bash
   kill 1234
   ```

6. **Q:** Which command starts a process with lower priority?
   **A:**
   ```bash
   nice -n 10 <command>
   ```

7. **Q:** Which command searches recursively with extended regex?
   **A:**
   ```bash
   grep -E -r 'pattern' <path>
   ```

8. **Q:** In `vi`, how do you save and quit?
   **A:**
   ```vim
   :wq
   ```

---

## 4. TOPIC 104: Devices, Linux Filesystems, FHS

1. **Q:** Which command creates an ext4 filesystem?
   **A:**
   ```bash
   mkfs.ext4 /dev/sdXN
   ```

2. **Q:** Which command checks ext filesystems for errors?
   **A:**
   ```bash
   fsck.ext4 /dev/sdXN
   ```

3. **Q:** Which command mounts all filesystems from `/etc/fstab`?
   **A:**
   ```bash
   mount -a
   ```

4. **Q:** Which command reports user/group quota usage?
   **A:**
   ```bash
   repquota -a
   ```

5. **Q:** How do you set SGID on a directory?
   **A:**
   ```bash
   chmod g+s /shared_dir
   ```

6. **Q:** What is the difference between hard and symbolic links?
   **A:** Hard links point to the same inode; symbolic links are separate files that store a pathname.

7. **Q:** Which FHS path stores variable log data?
   **A:**
   ```text
   /var/log
   ```

---

## 5. TOPIC 105: Shells and Shell Scripting

1. **Q:** Which file defines system-wide shell environment settings?
   **A:**
   ```text
   /etc/profile
   ```

2. **Q:** Which command lists shell aliases?
   **A:**
   ```bash
   alias
   ```

3. **Q:** How do you make a script executable?
   **A:**
   ```bash
   chmod +x script.sh
   ```

4. **Q:** Which shebang selects Bash explicitly?
   **A:**
   ```bash
   #!/bin/bash
   ```

5. **Q:** Which command runs SQL directly from shell in MariaDB/MySQL?
   **A:**
   ```bash
   mysql -e 'SELECT NOW();'
   ```

---

## 6. TOPIC 106: User Interfaces and Desktops

1. **Q:** Which command configures keyboard layout for X?
   **A:**
   ```bash
   setxkbmap us
   ```

2. **Q:** Which command reads X server log output via systemd journal?
   **A:**
   ```bash
   journalctl -u display-manager
   ```

3. **Q:** Which display manager could be enabled for graphical login?
   **A:** `gdm`, `lightdm`, or `sddm` (depends on distro).

4. **Q:** Where are X11 default configuration snippets often stored?
   **A:**
   ```text
   /etc/X11/xorg.conf.d/
   ```

5. **Q:** Which variable commonly controls interface language?
   **A:**
   ```text
   LANG
   ```

---

## 7. TOPIC 107: Administrative Tasks

1. **Q:** Which command creates a new user with home directory?
   **A:**
   ```bash
   useradd -m <username>
   ```

2. **Q:** Which command changes account aging/password policy?
   **A:**
   ```bash
   chage <username>
   ```

3. **Q:** Which file stores password aging defaults?
   **A:**
   ```text
   /etc/login.defs
   ```

4. **Q:** Which command edits a user’s crontab?
   **A:**
   ```bash
   crontab -e
   ```

5. **Q:** Which command runs a one-time scheduled job?
   **A:**
   ```bash
   at 14:30
   ```

6. **Q:** Which command generates locales after changing `/etc/locale.gen`?
   **A:**
   ```bash
   locale-gen
   ```

---

## 8. TOPIC 108: Essential System Services

1. **Q:** Which command shows the current system time and NTP status?
   **A:**
   ```bash
   timedatectl
   ```

2. **Q:** Which command displays kernel ring buffer messages?
   **A:**
   ```bash
   dmesg
   ```

3. **Q:** Where does traditional rsyslog configuration live?
   **A:**
   ```text
   /etc/rsyslog.conf
   ```

4. **Q:** Which command tests local mail transfer via sendmail interface?
   **A:**
   ```bash
   sendmail -v user@example.com
   ```

5. **Q:** Which command prints files from command line (CUPS)?
   **A:**
   ```bash
   lp file.txt
   ```

---

## 9. TOPIC 109: Networking Fundamentals

1. **Q:** Which command shows IP addresses for interfaces?
   **A:**
   ```bash
   ip addr show
   ```

2. **Q:** Which command shows the routing table?
   **A:**
   ```bash
   ip route
   ```

3. **Q:** Which command checks DNS resolution for a hostname?
   **A:**
   ```bash
   dig example.com
   ```

4. **Q:** Which file defines DNS resolver nameservers?
   **A:**
   ```text
   /etc/resolv.conf
   ```

5. **Q:** Which command tests remote TCP connectivity and can scan ports?
   **A:**
   ```bash
   nc -zv host 22
   ```

---

## 10. TOPIC 110: Security

1. **Q:** Which command changes file mode bits?
   **A:**
   ```bash
   chmod 640 file
   ```

2. **Q:** Which command changes file ownership?
   **A:**
   ```bash
   chown user:group file
   ```

3. **Q:** Which command lists open network sockets and listening services?
   **A:**
   ```bash
   ss -tulpen
   ```

4. **Q:** Which command securely copies files over SSH?
   **A:**
   ```bash
   scp local.txt user@host:/tmp/
   ```

5. **Q:** Which command symmetrically encrypts a file with GPG?
   **A:**
   ```bash
   gpg -c secret.txt
   ```

6. **Q:** Which command creates an SHA-256 checksum?
   **A:**
   ```bash
   sha256sum file.iso
   ```

---

## Final Study Note

For exam prep, prioritize higher-weight objectives first, then practice commands repeatedly on a live Linux VM so syntax, options, and file locations become automatic.
