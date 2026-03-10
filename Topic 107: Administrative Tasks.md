# TOPIC 107: Administrative Tasks

Reference: LPIC-1 Objectives V5.0: https://wiki.lpi.org/wiki/LPIC-1_Objectives_V5.0

## Covered Key Areas (weighted)

- **107.1 Manage user and group accounts and related system files** *(Weight: 5)*
- **107.2 Automate system administration tasks by scheduling jobs** *(Weight: 4)*
- **107.3 Localization and internationalization** *(Weight: 3)*

## Numbered Table of Content

1. TOPIC 107: Administrative Tasks
   1. 107.1 Manage user and group accounts and related system files
   2. 107.2 Automate system administration tasks by scheduling jobs
   3. 107.3 Localization and internationalization

---

## 107.1 Manage user and group accounts and related system files

### Key Areas

- Create, modify, lock, and remove user accounts and groups.
- Manage password aging, defaults, and account policy.
- Understand account databases and shadow password handling.
- Configure skeleton files and default user-creation behavior.

### Key Commands

```format
useradd
usermod
userdel
passwd
chage
groupadd
groupmod
groupdel
id
su
sudo
```

### Key Paths

```format
/etc/passwd
/etc/shadow
/etc/group
/etc/gshadow
/etc/default/useradd
/etc/login.defs
/etc/skel/
```

### Summary

This is one of the highest-weight objectives in 102. Expect operational tasks on account lifecycle, password policy, and file-level understanding of identity databases.

### Possible Exam Questions

1. Which file contains hashed user passwords?
2. How do you force a user to change password at next login?
3. What is the effect of locking an account with `usermod`?
4. Which files define default settings used by `useradd`?

---

## 107.2 Automate system administration tasks by scheduling jobs

### Key Areas

- Schedule recurring jobs with `cron` and one-time jobs with `at`.
- Manage per-user and system-wide crontab syntax.
- Control which users may use scheduling tools.
- Verify and troubleshoot job execution outcomes.

### Key Commands

```format
crontab
at
atq
atrm
systemctl status cron
systemctl status crond
```

### Key Paths

```format
/etc/crontab
/etc/cron.d/
/etc/cron.hourly/
/etc/cron.daily/
/etc/cron.weekly/
/etc/cron.monthly/
/var/spool/cron/
/etc/at.allow
/etc/at.deny
/etc/cron.allow
/etc/cron.deny
```

### Summary

This objective combines syntax knowledge with practical operations. Be comfortable building schedules, checking queues, and understanding system-wide vs user-specific job execution.

### Possible Exam Questions

1. What are the five time fields in a standard crontab entry?
2. How does `/etc/crontab` differ from user crontabs?
3. Which command lists pending `at` jobs?
4. How can you restrict cron usage to specific users?

---

## 107.3 Localization and internationalization

### Key Areas

- Configure locale, language, and character encoding behavior.
- Understand `LANG`, `LC_*`, and locale precedence.
- Set timezone and verify date/time regional presentation.

### Key Commands

```format
locale
localectl
timedatectl
dpkg-reconfigure locales
```

### Key Paths

```format
/etc/locale.conf
/etc/default/locale
/etc/timezone
/usr/share/zoneinfo/
```

### Summary

Localization tasks appear regularly in administration: generating locales, setting defaults, and ensuring programs use the right language, collation, and time conventions.

### Possible Exam Questions

1. What is the purpose of `LC_ALL`?
2. How can you view currently effective locale values?
3. Which command sets the system timezone on a systemd host?
4. Where are timezone definitions stored?
