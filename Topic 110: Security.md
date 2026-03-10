# TOPIC 110: Security

Reference: LPIC-1 Objectives V5.0: https://wiki.lpi.org/wiki/LPIC-1_Objectives_V5.0

## Covered Key Areas (weighted)

- **110.1 Perform security administration tasks** *(Weight: 3)*
- **110.2 Setup host security** *(Weight: 3)*
- **110.3 Securing data with encryption** *(Weight: 4)*

## Numbered Table of Content

1. TOPIC 110: Security
   1. 110.1 Perform security administration tasks
   2. 110.2 Setup host security
   3. 110.3 Securing data with encryption

---

## 110.1 Perform security administration tasks

### Key Areas

- Apply least-privilege principles and secure account practices.
- Audit privileged access and service exposure.
- Understand password policy, account locking, and basic hardening workflow.

### Key Commands

```format
passwd
chage
sudo
visudo
last
lastb
who
w
```

### Key Paths

```format
/etc/sudoers
/etc/sudoers.d/
/etc/shadow
/etc/login.defs
/var/log/auth.log
/var/log/secure
```

### Summary

This objective focuses on day-to-day security hygiene: account policy, privilege control, and auditing user activity.

### Possible Exam Questions

1. Why should `visudo` be used instead of editing `/etc/sudoers` directly?
2. Which logs typically contain authentication failures?
3. How do you enforce password aging on Linux accounts?
4. What is the security principle of least privilege?

---

## 110.2 Setup host security

### Key Areas

- Configure basic packet filtering and host access restrictions.
- Disable unnecessary network services and verify listening ports.
- Understand TCP wrapper concepts where applicable.

### Key Commands

```format
iptables
nft
ufw
firewall-cmd
ss
systemctl
```

### Key Paths

```format
/etc/hosts.allow
/etc/hosts.deny
/etc/nftables.conf
/etc/iptables/
```

### Summary

Expect baseline host-hardening tasks: limit exposed services, apply filtering, and verify resulting network surface.

### Possible Exam Questions

1. Which command can list listening sockets to verify exposed services?
2. What is the purpose of default-deny firewall policy?
3. How do `/etc/hosts.allow` and `/etc/hosts.deny` conceptually work?
4. Why should unused services be disabled?

---

## 110.3 Securing data with encryption

### Key Areas

- Use OpenSSH for secure remote access and key-based authentication.
- Understand GPG concepts for signing and encrypting data.
- Use TLS certificate basics and verify secure channels.

### Key Commands

```format
ssh
scp
sftp
ssh-keygen
ssh-agent
ssh-add
gpg
openssl
```

### Key Paths

```format
~/.ssh/id_rsa
~/.ssh/id_ed25519
~/.ssh/authorized_keys
~/.ssh/config
/etc/ssh/sshd_config
/etc/ssl/
~/.gnupg/
```

### Summary

This high-weight objective requires practical encryption usage: secure remote login, key management, and command-line cryptographic tooling basics.

### Possible Exam Questions

1. How does key-based SSH authentication work at a high level?
2. Which file on a server stores allowed public keys for a user?
3. What is the difference between encryption and signing with GPG?
4. Which OpenSSL command can inspect certificate details?
