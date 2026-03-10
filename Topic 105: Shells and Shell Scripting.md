# TOPIC 105: Shells and Shell Scripting

Reference: LPIC-1 Objectives V5.0: https://wiki.lpi.org/wiki/LPIC-1_Objectives_V5.0

## Covered Key Areas (weighted)

- **105.1 Customize and use the shell environment** *(Weight: 4)*
- **105.2 Customize or write simple scripts** *(Weight: 4)*
- **105.3 SQL data management** *(Weight: 2)*

## Numbered Table of Content

1. TOPIC 105: Shells and Shell Scripting
   1. 105.1 Customize and use the shell environment
   2. 105.2 Customize or write simple scripts
   3. 105.3 SQL data management

---

## 105.1 Customize and use the shell environment

### Key Areas

- Work with shell types and login/non-login shell behavior.
- Configure environment and shell variables, aliases, and functions.
- Use command history and shell expansion safely and efficiently.
- Understand startup files and where to persist interactive customizations.

### Key Commands

```format
printenv
env
set
unset
export
alias
unalias
history
source
.
```

### Key Paths

```format
/etc/profile
/etc/bash.bashrc
~/.bash_profile
~/.bash_login
~/.profile
~/.bashrc
~/.bash_logout
~/.inputrc
```

### Summary

This objective is heavily weighted and focuses on efficient shell usage in daily administration: startup behavior, variable scope, history, and customization persistence.

### Possible Exam Questions

1. What is the difference between a shell variable and an environment variable?
2. Which startup file is usually used for interactive Bash aliases?
3. How do `source` and executing a script differ for variable persistence?
4. How do you remove an alias during the current shell session?

---

## 105.2 Customize or write simple scripts

### Key Areas

- Create executable shell scripts with shebang and proper permissions.
- Use positional parameters and shell built-ins to handle input.
- Implement control structures (`if`, `case`, `for`, `while`) and exit codes.
- Use command substitution, quoting, redirection, and basic text processing.

### Key Commands

```format
chmod
test
[
]
read
echo
printf
expr
let
basename
dirname
xargs
```

### Key Paths

```format
#!/bin/bash
/usr/local/bin/
~/bin/
```

### Summary

This objective expects you to read and write practical administrative scripts. You should be comfortable with flow control, safe quoting, parameter handling, and predictable exit statuses.

### Possible Exam Questions

1. Why is `#!/bin/bash` placed at the top of a script?
2. How do `$1`, `$2`, and `$#` work in scripts?
3. What is the difference between `"$var"` and `$var` in command arguments?
4. How can a script return success or failure to the calling shell?

---

## 105.3 SQL data management

### Key Areas

- Understand relational database fundamentals: tables, rows, columns, keys.
- Perform basic SQL operations with `SELECT`, `INSERT`, `UPDATE`, `DELETE`.
- Use command-line clients to connect, query, and inspect simple datasets.
- Understand practical admin use cases (inventory, logs, account data).

### Key Commands

```format
mysql
mariadb
sqlite3
SELECT
INSERT
UPDATE
DELETE
CREATE TABLE
DROP TABLE
```

### Key Paths

```format
/etc/mysql/
/var/lib/mysql/
~/.my.cnf
```

### Summary

This objective is lighter than shell topics but still exam-relevant. Focus on SQL basics and command-line querying rather than deep database internals.

### Possible Exam Questions

1. Which SQL statement retrieves rows from a table?
2. What is the purpose of a primary key?
3. How would you update a single row using a `WHERE` clause?
4. Which command-line tool can query a local SQLite database file?
