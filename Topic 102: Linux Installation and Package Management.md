# TOPIC 102: Linux Installation and Package Management

Reference: LPIC-1 Objectives V5.0: https://wiki.lpi.org/wiki/LPIC-1_Objectives_V5.0

## Covered Key Areas (weighted)

- **102.1 Design hard disk layout** *(Weight: 2)*
- **102.2 Install a boot manager** *(Weight: 2)*
- **102.3 Manage shared libraries** *(Weight: 1)*
- **102.4 Use Debian package management** *(Weight: 3)*
- **102.5 Use RPM and YUM package management** *(Weight: 3)*
- **102.6 Linux as a virtualization guest** *(Weight: 1)*

---

## 102.1 Design hard disk layout

### Key Areas

- Allocate partitions for system and data based on purpose and expected growth.
- Understand partitioning schemes:
  - MBR (msdos)
  - GPT
- Use separate filesystems where appropriate (`/`, `/boot`, `/home`, `/var`, `/tmp`).
- Understand swap sizing and usage strategies.
- Recognize LVM concepts for flexible logical storage.
- Consider mount options and filesystem choices for reliability and performance.

### Key Commands

```bash
lsblk
blkid
fdisk
gdisk
parted
pvcreate
vgcreate
lvcreate
mkfs.ext4
mkswap
swapon
```

### Key Paths

```text
/etc/fstab
/proc/partitions
/proc/swaps
/dev/sd*
/dev/nvme*
/dev/mapper/
```

### Summary

Objective 102.1 focuses on building a sustainable storage layout before and during installation. You should be able to choose between MBR/GPT, size core mount points, add swap, and understand when LVM improves maintainability (resizing, snapshots, migration).

### Possible Exam Questions

1. When is GPT preferred over MBR?
2. What are practical reasons to place `/var` or `/home` on separate partitions?
3. Which command initializes a physical volume for LVM?
4. Which file defines persistent mount points and mount options?

---

## 102.2 Install a boot manager

### Key Areas

- Understand boot manager role in BIOS and UEFI systems.
- Install and reinstall GRUB2 to correct device and firmware targets.
- Configure and maintain boot menu entries and defaults.
- Pass temporary or persistent kernel parameters.
- Know bootloader file locations across major distributions.

### Key Commands

```bash
grub-install
grub-mkconfig
grub2-install
grub2-mkconfig
update-grub
efibootmgr
```

### Key Paths

```text
/boot
/boot/grub/
/boot/grub2/
/boot/efi/
/etc/default/grub
/etc/grub.d/
```

### Summary

Objective 102.2 expects you to handle bootloader deployment and repair confidently. You should know how GRUB2 is installed for legacy BIOS vs UEFI, where configuration snippets live, and how to regenerate final boot config after changes.

### Possible Exam Questions

1. Which command installs GRUB to a specific disk in BIOS mode?
2. Where are default GRUB kernel options usually configured?
3. What command regenerates GRUB config on Debian-based systems?
4. Why might `efibootmgr` be needed after a bootloader reinstall?

---

## 102.3 Manage shared libraries

### Key Areas

- Understand dynamic vs static linking.
- Locate shared libraries and linker search behavior.
- Maintain runtime linker cache.
- Inspect binary dependencies.
- Configure additional library search paths safely.

### Key Commands

```bash
ldd
ldconfig
readelf -d
objdump -p
```

### Key Paths

```text
/lib
/lib64
/usr/lib
/usr/lib64
/etc/ld.so.conf
/etc/ld.so.conf.d/
/etc/ld.so.cache
```

### Summary

Objective 102.3 checks your ability to troubleshoot runtime dependency issues. You should understand how binaries locate `.so` files, how to inspect linked libraries, and when to refresh linker cache after adding library paths.

### Possible Exam Questions

1. What is the purpose of `ldconfig`?
2. Which command quickly lists shared library dependencies of a binary?
3. Where are additional dynamic linker path fragments commonly stored?
4. What is a common risk of modifying linker search paths globally?

---

## 102.4 Use Debian package management

### Key Areas

- Perform package operations with low-level and high-level tools.
- Query package database and package contents.
- Install, remove, and purge packages safely.
- Work with package repositories and package cache.
- Understand package states and dependency handling.

### Key Commands

```bash
dpkg -i package.deb
dpkg -r package
dpkg -P package
dpkg -l
dpkg -s package
dpkg -L package
dpkg -S /path/to/file
apt update
apt install package
apt remove package
apt purge package
apt upgrade
apt-cache search keyword
apt-cache policy package
```

### Key Paths

```text
/etc/apt/sources.list
/etc/apt/sources.list.d/
/var/lib/dpkg/
/var/lib/apt/
/var/cache/apt/archives/
```

### Summary

Objective 102.4 validates practical Debian package administration. You should know when to use `dpkg` directly (local `.deb`, package database queries) and when to use `apt` for dependency-aware installation, repository synchronization, and upgrades.

### Possible Exam Questions

1. What is the difference between `dpkg -r` and `dpkg -P`?
2. Which command updates repository metadata without installing upgrades?
3. How do you find which installed package owns a given file path?
4. Where are additional APT repository definitions commonly stored?

---

## 102.5 Use RPM and YUM package management

### Key Areas

- Install, upgrade, remove, and query RPM packages.
- Verify packages and inspect package metadata.
- Use dependency-aware frontends (`yum`, `dnf`, `zypper`) for repositories.
- Search, install, and update packages from configured repos.
- Understand repository configuration and GPG signature verification.

### Key Commands

```bash
rpm -ivh package.rpm
rpm -Uvh package.rpm
rpm -e package
rpm -qa
rpm -qi package
rpm -ql package
rpm -qf /path/to/file
rpm -V package
yum install package
yum remove package
yum update
yum search keyword
dnf install package
dnf upgrade
zypper search package
zypper install package
```

### Key Paths

```text
/etc/yum.conf
/etc/yum.repos.d/
/etc/dnf/dnf.conf
/etc/dnf/repos.d/
/etc/zypp/
/var/lib/rpm/
```

### Summary

Objective 102.5 focuses on RPM-family package management across enterprise distributions. You should be able to use `rpm` for low-level operations and `yum`/`dnf`/`zypper` for repository-aware dependency resolution, updates, and troubleshooting.

### Possible Exam Questions

1. What is the functional difference between `rpm -ivh` and `rpm -Uvh`?
2. Which command checks package file integrity after installation?
3. Where are YUM/DNF repository definitions stored?
4. Why are `yum` or `dnf` usually preferred over raw `rpm` for normal installs?

---

## 102.6 Linux as a virtualization guest

### Key Areas

- Understand guest additions and paravirtualized drivers.
- Verify resource visibility in virtualized environments.
- Manage cloud and virtual machine initialization basics.
- Know common hypervisor-specific integration tools.

### Key Commands

```bash
systemd-detect-virt
lscpu
lsmod
dmesg | grep -Ei 'virt|hypervisor'
uname -r
```

### Key Paths

```text
/dev/vda*
/dev/xvda*
/etc/cloud/
/var/log/cloud-init.log
```

### Summary

Objective 102.6 checks whether you can operate Linux correctly when running as a guest OS. Focus on recognizing virtualization platforms, ensuring proper guest drivers/tools are present, and validating that storage/network devices are detected as expected.

### Possible Exam Questions

1. Which command quickly detects whether Linux is running in a VM?
2. Why are paravirtualized drivers important in guests?
3. What device naming patterns are common for virtual disks?
4. Where can cloud-init behavior often be reviewed?

---

## Study Tip for Weighting

Spend most of your study time on the highest-weight objectives:

- **102.4** and **102.5** (package management workflows and troubleshooting),
- then **102.1** and **102.2** (storage and bootloader design/repair),
- finally reinforce **102.3** and **102.6** as lighter objectives.
