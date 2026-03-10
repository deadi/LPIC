# TOPIC 101: System Architecture

Reference: LPIC-1 Objectives V5.0: https://wiki.lpi.org/wiki/LPIC-1_Objectives_V5.0

## Covered Key Areas (weighted)

- **101.1 Determine and configure hardware settings** *(Weight: 2)*
- **101.2 Boot the system** *(Weight: 3)*
- **101.3 Change runlevels / boot targets and shutdown or reboot system** *(Weight: 3)*

---

## 101.1 Determine and configure hardware settings

### Key Areas

- Enable/disable integrated peripherals and extension cards.
- Understand and inspect device resources:
  - IRQs (interrupt request)
  - DMA channels (direct memory access)
  - I/O ports
  - memory addresses
- Identify hardware characteristics and attached devices.
- Work with Linux device information interfaces.

### Key Commands

```bash
lspci
lsusb
lsblk
lscpu
lsmem
lshw
hwinfo
modprobe
lsmod
```

### Key Paths

```text
/proc
/proc/interrupts
/proc/ioports
/proc/dma
/proc/meminfo
/sys
/dev
```

### Summary

Objective 101.1 is focused on **recognizing hardware and validating that Linux sees and configures it correctly**. You should be comfortable checking buses (`PCI`, `USB`), storage, CPU/memory, and kernel module state. You should also know how to read low-level kernel-exported hardware data via `procfs` and `sysfs`.

### Possible Exam Questions

1. Which command lists PCI devices and their IDs?
2. Where can you view current IRQ assignments?
3. Which command loads a kernel module at runtime?
4. What is the difference between information in `/proc` and `/sys` for device discovery?

---

## 101.2 Boot the system

### Key Areas

- BIOS vs UEFI roles in system startup.
- Bootloader stages and GRUB2 behavior.
- Kernel loading and initramfs/initrd usage.
- Boot options and temporary kernel parameter changes.
- Identify and troubleshoot common boot issues.

### Key Commands

```bash
grub-install
grub-mkconfig
grub2-mkconfig
update-grub
journalctl -b
dmesg
cat /proc/cmdline
```

### Key Paths

```text
/boot
/boot/grub
/boot/grub2
/boot/efi
/etc/default/grub
/etc/grub.d/
```

### Summary

Objective 101.2 validates your understanding of the **end-to-end boot pipeline**: firmware initializes hardware, bootloader loads kernel + initramfs, and early userspace transitions into the real root filesystem. You should know where GRUB configuration comes from and how to regenerate it safely.

### Possible Exam Questions

1. What is the purpose of `initramfs` during early boot?
2. Which file usually contains default GRUB kernel options?
3. How do you inspect kernel parameters used in the current boot?
4. What command is commonly used to regenerate GRUB configuration on Debian-based systems?

---

## 101.3 Change runlevels / boot targets and shutdown or reboot system

### Key Areas

- SysV init runlevels and their historical meaning.
- `systemd` targets and mapping from classic runlevels.
- Inspect and set default boot target.
- Switch targets for rescue/multi-user/graphical operation.
- Proper shutdown and reboot procedures.

### Key Commands

```bash
systemctl get-default
systemctl set-default multi-user.target
systemctl isolate rescue.target
systemctl reboot
systemctl poweroff
shutdown -r now
shutdown -h now
```

### Key Paths

```text
/etc/inittab
/etc/systemd/system/default.target
/usr/lib/systemd/system/
/etc/systemd/system/
```

### Summary

Objective 101.3 expects you to manage **runtime operating modes and controlled system state transitions**. In modern distributions, this means using `systemd` targets (`rescue.target`, `multi-user.target`, `graphical.target`) and safe reboot/shutdown commands. You should also understand legacy runlevel terminology for compatibility and exam context.

### Possible Exam Questions

1. Which command shows the current default `systemd` target?
2. How can you boot into a rescue environment from a running system?
3. What target is the usual equivalent of classic runlevel 3?
4. Why is `shutdown` preferred over abrupt power loss?

---

## Quick Comparison: Legacy Runlevels vs systemd Targets

```text
runlevel 0  -> poweroff.target
runlevel 1  -> rescue.target
runlevel 3  -> multi-user.target
runlevel 5  -> graphical.target
runlevel 6  -> reboot.target
```

## Study Tip for Weighting

Because **101.2** and **101.3** have higher weight than **101.1**, spend proportionally more time practicing:

- bootloader recovery and boot parameter edits,
- target switching and recovery boot modes,
- safe serviceable reboot/shutdown workflows.
