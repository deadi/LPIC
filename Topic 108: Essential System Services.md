# TOPIC 108: Essential System Services

Reference: LPIC-1 Objectives V5.0: https://wiki.lpi.org/wiki/LPIC-1_Objectives_V5.0

## Covered Key Areas (weighted)

- **108.1 Maintain system time** *(Weight: 3)*
- **108.2 System logging** *(Weight: 3)*
- **108.3 Mail Transfer Agent (MTA) basics** *(Weight: 3)*
- **108.4 Manage printers and printing** *(Weight: 2)*

## Numbered Table of Content

1. TOPIC 108: Essential System Services
   1. 108.1 Maintain system time
   2. 108.2 System logging
   3. 108.3 Mail Transfer Agent (MTA) basics
   4. 108.4 Manage printers and printing

---

## 108.1 Maintain system time

### Key Areas

- Understand hardware clock vs system clock and synchronization flow.
- Configure and verify NTP/time sync services.
- Adjust timezone and validate consistent system timestamps.

### Key Commands

```format
date
hwclock
timedatectl
ntpq
chronyc
```

### Key Paths

```format
/etc/localtime
/etc/timezone
/etc/chrony/
/etc/ntp.conf
```

### Summary

Time accuracy is operationally critical for logs, authentication, and distributed services. Know sync tooling and clock hierarchy.

### Possible Exam Questions

1. What is the difference between the hardware clock and system clock?
2. Which command shows NTP synchronization state on systemd systems?
3. Where are timezone definitions stored?
4. Why is time synchronization important for log correlation?

---

## 108.2 System logging

### Key Areas

- Understand syslog/journald concepts, facilities, and priorities.
- Configure log routing and persistent storage.
- Inspect logs and filter by service, time, and severity.
- Rotate, retain, and manage log size.

### Key Commands

```format
journalctl
logger
rsyslogd
syslog-ng
logrotate
```

### Key Paths

```format
/etc/rsyslog.conf
/etc/rsyslog.d/
/etc/syslog-ng/
/etc/systemd/journald.conf
/var/log/
/etc/logrotate.conf
/etc/logrotate.d/
```

### Summary

This objective expects practical logging administration: collecting, querying, and rotating logs for reliability and compliance.

### Possible Exam Questions

1. Which command reads systemd journal entries?
2. Where are `logrotate` service-specific policies commonly stored?
3. What is the purpose of syslog facilities and priorities?
4. How can you send a custom message into syslog from shell?

---

## 108.3 Mail Transfer Agent (MTA) basics

### Key Areas

- Understand local mail delivery pipeline and MTA purpose.
- Configure local aliases and mail forwarding basics.
- Use simple mail queue inspection and delivery troubleshooting.

### Key Commands

```format
mail
mailq
newaliases
sendmail
postfix
exim
```

### Key Paths

```format
/etc/aliases
/etc/postfix/
/etc/exim4/
/var/spool/mail/
```

### Summary

LPIC-1 emphasizes basic MTA operation (especially local system mail), alias handling, and queue awareness over advanced relay design.

### Possible Exam Questions

1. What command rebuilds alias databases after editing `/etc/aliases`?
2. Where is local user mailbox data commonly stored?
3. What is the role of an MTA in Linux?
4. Which command shows queued mail messages?

---

## 108.4 Manage printers and printing

### Key Areas

- Configure print services and queues.
- Submit, inspect, and cancel print jobs.
- Set default printers and troubleshoot queue states.

### Key Commands

```format
lp
lpstat
lpr
lprm
lpq
cancel
cupsd
```

### Key Paths

```format
/etc/cups/
/etc/printcap
/var/spool/cups/
```

### Summary

Know classic and CUPS-based printing workflows: queue management, job control, and service configuration basics.

### Possible Exam Questions

1. Which command lists printer queues and status?
2. How can you cancel a submitted print job?
3. Which service commonly manages printing on modern Linux systems?
4. Where is CUPS configuration stored?
