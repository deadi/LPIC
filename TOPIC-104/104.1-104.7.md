# TOPIC 104: Devices, Linux Filesystems, Filesystem Hierarchy Standard

Reference: LPIC-1 Objectives V5.0: https://wiki.lpi.org/wiki/LPIC-1_Objectives_V5.0

## Covered Key Areas (weighted)

- **104.1 Create partitions and filesystems** *(Weight: 2)*
- **104.2 Maintain the integrity of filesystems** *(Weight: 2)*
- **104.3 Control mounting and unmounting of filesystems** *(Weight: 3)*
- **104.4 Manage disk quotas** *(Weight: 1)*
- **104.5 Manage file permissions and ownership** *(Weight: 3)*
- **104.6 Create and change hard and symbolic links** *(Weight: 2)*
- **104.7 Find system files and place files in the correct location** *(Weight: 2)*

---

## 104.1 Create partitions and filesystems

### Key Areas

- Create and modify partition tables with MBR/GPT-aware tools.
- Build filesystems for Linux workloads (ext4, XFS, vfat, swap).
- Understand UUIDs, labels, and persistent block device naming.
- Prepare filesystems for mount and boot workflows.

### Key Commands

```bash
lsblk
blkid
fdisk
gdisk
parted
mkfs.ext4
mkfs.xfs
mkfs.vfat
mkswap
swapon
wipefs
```

### Key Paths

```text
/dev/sd*
/dev/nvme*
/dev/mapper/
/dev/disk/by-uuid/
/dev/disk/by-label/
/etc/fstab
```

### Summary

This objective validates storage provisioning fundamentals: identify devices, create partitions, format with the right filesystem, and prepare persistent mounts with UUID/label references.

### Possible Exam Questions

1. Why is UUID generally preferred over `/dev/sdX` naming in `fstab`?
2. Which command creates an ext4 filesystem on `/dev/sdb1`?
3. What command shows filesystem UUID and type information?
4. When would you choose GPT instead of MBR?

---

## 104.2 Maintain the integrity of filesystems

### Key Areas

- Check and repair filesystem consistency using appropriate tooling.
- Understand journaling and clean/unclean shutdown implications.
- Tune filesystem behavior (check intervals, reserved blocks, labels).
- Recognize when a filesystem must be unmounted before repair.

### Key Commands

```bash
fsck
e2fsck
tune2fs
dumpe2fs
xfs_repair
xfs_info
badblocks
```

### Key Paths

```text
/etc/fstab
/lost+found
/proc/mounts
```

### Summary

Objective 104.2 focuses on keeping filesystems reliable over time. You should know safe check/repair workflows, when to force checks, and which tools are filesystem-specific.

### Possible Exam Questions

1. Why should you avoid running `fsck` on a mounted read-write filesystem?
2. Which tool is commonly used to inspect ext filesystem superblock information?
3. What is the purpose of `tune2fs -c` or `-i` settings?
4. Which command is used to repair XFS filesystems?

---

## 104.3 Control mounting and unmounting of filesystems

### Key Areas

- Mount and unmount filesystems manually and automatically.
- Configure persistent mounts in `fstab` with correct options.
- Use mount options for security and behavior control.
- Handle temporary mounts, bind mounts, and remounting.

### Key Commands

```bash
mount
umount
findmnt
mount -a
systemctl daemon-reload
```

### Key Paths

```text
/etc/fstab
/etc/mtab
/proc/mounts
/media/
/mnt/
```

### Summary

This high-weight objective emphasizes practical mount administration. Expect tasks around `fstab` syntax, option selection (`defaults`, `noexec`, `nosuid`, `nodev`, `ro`, `rw`), and troubleshooting failed mounts.

### Possible Exam Questions

1. What does `mount -a` do, and when is it useful?
2. Which file defines persistent mount points across reboots?
3. What is the difference between `/etc/mtab` and `/proc/mounts`?
4. Why use `noexec` on removable-media mount points?

---

## 104.4 Manage disk quotas

### Key Areas

- Enable user/group quotas per filesystem.
- Build and check quota databases.
- Assign soft/hard limits and grace periods.
- Report quota usage for users and groups.

### Key Commands

```bash
quotaon
quotaoff
quotacheck
edquota
setquota
repquota
quota
```

### Key Paths

```text
/etc/fstab
aquota.user
aquota.group
```

### Summary

Objective 104.4 is smaller in weight but common in admin scenarios. Know the activation flow: enable mount options, build quota files, turn quotas on, then define limits and verify enforcement.

### Possible Exam Questions

1. Which `fstab` options are used to enable user and group quotas?
2. What does `quotacheck` create/update?
3. How do soft and hard limits differ?
4. Which command shows quota usage for all users on a filesystem?

---

## 104.5 Manage file permissions and ownership

### Key Areas

- Read and modify Unix permission bits (`rwx`) for files/directories.
- Use symbolic and octal modes with `chmod`.
- Set ownership and group membership for filesystem objects.
- Apply special permissions: SUID, SGID, sticky bit.
- Understand default permission behavior and `umask`.

### Key Commands

```bash
chmod
chown
chgrp
umask
id
getfacl
setfacl
```

### Key Paths

```text
/etc/passwd
/etc/group
/etc/login.defs
```

### Summary

This is a core security objective with high exam relevance. You should be fluent in octal/symbolic permissions, recursive ownership changes, and real-world effects of SUID/SGID/sticky bit settings.

### Possible Exam Questions

1. What permission mode corresponds to `rwxr-x---`?
2. What does the sticky bit on a shared directory like `/tmp` enforce?
3. How does SGID behave differently on executables vs directories?
4. What is the purpose of `umask`?

---

## 104.6 Create and change hard and symbolic links

### Key Areas

- Create hard links and symbolic links.
- Understand inode relationships and cross-filesystem restrictions.
- Identify broken symbolic links and relink safely.
- Recognize use cases for each link type.

### Key Commands

```bash
ln
ln -s
ls -li
readlink
find -L
```

### Key Paths

```text
/usr/bin/
/usr/sbin/
/etc/alternatives/
```

### Summary

Objective 104.6 checks link mechanics: hard links share inode/data, symlinks store a path reference. You should know limitations (e.g., hard links typically not across filesystems, not to directories in normal admin use).

### Possible Exam Questions

1. Which command creates a symbolic link named `current` to `release-2`?
2. Why can hard links not normally span filesystems?
3. How can you display inode numbers to verify hard links?
4. What happens when a symlink target is removed?

---

## 104.7 Find system files and place files in the correct location

### Key Areas

- Apply Filesystem Hierarchy Standard (FHS) placement rules.
- Distinguish static vs variable data, host-specific vs shareable data.
- Locate binaries, libraries, configs, logs, and runtime state.
- Use file-location tools for troubleshooting and scripting.

### Key Commands

```bash
find
locate
updatedb
which
whereis
type
```

### Key Paths

```text
/bin
/sbin
/usr/bin
/usr/sbin
/usr/lib
/etc
/var
/var/log
/var/lib
/home
/root
/tmp
/opt
```

### Summary

This objective connects technical file discovery with standards-based placement. For the exam, memorize common FHS directories and understand where packages, configs, logs, and variable application data should live.

### Possible Exam Questions

1. According to FHS, where should host-specific system configuration files be stored?
2. What is the typical role of `/var/lib` vs `/var/log`?
3. Which command database must be refreshed for `locate` to find new files?
4. Where should optional third-party application packages typically be installed?
