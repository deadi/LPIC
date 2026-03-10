# TOPIC 103: GNU and Unix Commands

Reference: LPIC-1 Objectives V5.0: https://wiki.lpi.org/wiki/LPIC-1_Objectives_V5.0

## Covered Key Areas (weighted)

- **103.1 Work on the command line** *(Weight: 4)*
- **103.2 Process text streams using filters** *(Weight: 3)*
- **103.3 Perform basic file management** *(Weight: 4)*
- **103.4 Use streams, pipes and redirects** *(Weight: 4)*
- **103.5 Create, monitor and kill processes** *(Weight: 4)*
- **103.6 Modify process execution priorities** *(Weight: 2)*
- **103.7 Search text files using regular expressions** *(Weight: 3)*
- **103.8 Perform basic file editing operations using vi** *(Weight: 3)*

---

## 103.1 Work on the command line

### Key Areas

- Interact with shells in interactive and non-interactive modes.
- Use command history, completion, quoting, and escaping.
- Work with environment variables and shell expansion.
- Execute commands with absolute and relative paths.
- Understand command lookup and return codes.

### Key Commands

```bash
pwd
cd
echo
history
env
export
which
type
man
help
```

### Key Paths

```text
/bin
/usr/bin
/etc/profile
/etc/bash.bashrc
~/.bashrc
~/.profile
```

### Summary

Objective 103.1 validates daily shell fluency. You should be fast with navigation, command discovery, quoting rules, variables, and shell startup files, since these skills are required in almost every other objective.

### Possible Exam Questions

1. What is the difference between single quotes and double quotes in the shell?
2. Which command shows whether a token is a shell builtin, alias, function, or binary?
3. Where is user-specific interactive shell configuration commonly stored?
4. What does an exit status of `0` indicate?

---

## 103.2 Process text streams using filters

### Key Areas

- Transform and extract data from plain-text streams.
- Combine filters to build reusable command pipelines.
- Sort, compare, and count output.
- Cut/select fields and format columns.
- Extract patterns and summarize log data.

### Key Commands

```bash
cat
less
head
tail
sort
uniq
wc
cut
paste
tr
sed
awk
nl
od
split
```

### Key Paths

```text
/usr/share/dict/
/var/log/
```

### Summary

Objective 103.2 focuses on text-processing workflows. The exam often expects you to combine multiple filters in one pipeline to produce exactly formatted output from structured or semi-structured text.

### Possible Exam Questions

1. How do `sort` and `uniq` typically work together to count duplicate lines?
2. Which command prints only the first 10 lines of a file by default?
3. What is a common use of `awk -F`?
4. How can you follow new lines appended to a log file in real time?

---

## 103.3 Perform basic file management

### Key Areas

- Create, copy, move, and remove files/directories.
- Work with globbing and recursive operations.
- Understand file timestamps and metadata inspection.
- Create and extract archives.
- Manage hard links and symbolic links.

### Key Commands

```bash
ls
cp
mv
rm
mkdir
rmdir
touch
file
stat
find
locate
tar
cpio
gzip
gunzip
bzip2
bunzip2
xz
unxz
ln
```

### Key Paths

```text
/etc/skel
/tmp
/var/tmp
/home
```

### Summary

Objective 103.3 checks whether you can safely manipulate filesystem objects and package data for transfer/backup. Expect practical questions around links, wildcard behavior, and archive/compression tool combinations.

### Possible Exam Questions

1. What is the difference between a hard link and a symbolic link?
2. Which command displays detailed metadata including inode and timestamps?
3. How do you create a compressed tar archive using gzip?
4. Why is recursive removal with `rm -r` considered risky?

---

## 103.4 Use streams, pipes and redirects

### Key Areas

- Redirect standard input, output, and error streams.
- Chain commands with pipes for staged processing.
- Append vs overwrite output targets.
- Combine output streams when needed.
- Use here-documents and here-strings in shell scripting.

### Key Commands

```bash
cmd > file
cmd >> file
cmd < file
cmd 2> err.log
cmd > out.log 2>&1
cmd1 | cmd2
tee
xargs
```

### Key Paths

```text
/dev/null
/dev/stdin
/dev/stdout
/dev/stderr
```

### Summary

Objective 103.4 is core shell plumbing. You should know descriptor basics (`0`, `1`, `2`), redirection order, and how to construct reliable pipelines that preserve or split output as required.

### Possible Exam Questions

1. What is the difference between `>` and `>>`?
2. How do you redirect both stdout and stderr to the same file?
3. What does `tee` do in a pipeline?
4. Why might `xargs` be needed after a filtering command?

---

## 103.5 Create, monitor and kill processes

### Key Areas

- Start jobs in foreground/background.
- Inspect running processes and process trees.
- Locate processes by name or attributes.
- Send signals for graceful or forceful termination.
- Use job control in interactive shells.

### Key Commands

```bash
ps
top
pgrep
pidof
pstree
jobs
bg
fg
nohup
kill
killall
pkill
```

### Key Paths

```text
/proc
/proc/<PID>/
```

### Summary

Objective 103.5 evaluates process lifecycle control. In exams, focus on interpreting `ps` output, selecting the correct signal (`TERM` vs `KILL`), and using shell job control safely.

### Possible Exam Questions

1. Which signal is sent by default when using `kill`?
2. How can you resume a stopped job in the background?
3. Which command finds process IDs by matching a command name pattern?
4. Why should `SIGKILL` usually be a last resort?

---

## 103.6 Modify process execution priorities

### Key Areas

- Understand scheduler niceness values.
- Start commands with custom nice values.
- Adjust priority of running processes.
- Recognize privileged vs unprivileged priority changes.

### Key Commands

```bash
nice
renice
ps -o pid,ni,comm
```

### Key Paths

```text
/proc/<PID>/stat
```

### Summary

Objective 103.6 covers CPU scheduling priority control. You should know that lower niceness means higher scheduling priority and that regular users cannot increase priority beyond allowed limits.

### Possible Exam Questions

1. What is the default niceness of a normal process?
2. Which command changes priority of an already running process?
3. Can an unprivileged user set a negative nice value?
4. How can you display niceness in process listings?

---

## 103.7 Search text files using regular expressions

### Key Areas

- Use basic and extended regular expressions.
- Match anchors, character classes, and quantifiers.
- Search recursively and invert matches.
- Count matches and print matching context.
- Apply regex with tools like `grep`, `sed`, and `awk`.

### Key Commands

```bash
grep
egrep
fgrep
grep -E
grep -F
grep -r
grep -n
grep -v
sed -n
awk
```

### Key Paths

```text
/etc
/var/log
```

### Summary

Objective 103.7 requires practical regex usage, not theory alone. You should be able to quickly build patterns for validation, extraction, and filtering tasks commonly seen in configuration files and logs.

### Possible Exam Questions

1. What is the difference between `grep -E` and `grep -F`?
2. How do you match lines that start with `root`?
3. Which option inverts matches in `grep`?
4. How can you print line numbers alongside matches?

---

## 103.8 Perform basic file editing operations using vi

### Key Areas

- Use vi/vim modes correctly (normal, insert, command-line).
- Navigate efficiently by line, word, and search patterns.
- Insert, delete, copy, and paste text.
- Save, quit, and recover from common editing mistakes.
- Perform global replacements.

### Key Commands

```bash
vi file.txt
vim file.txt
```

```vim
h j k l
i a o
x dd yy p
u Ctrl-r
:w :q :wq :q!
/pattern ?pattern
:%s/old/new/g
```

### Key Paths

```text
~/.vimrc
/etc/vimrc
```

### Summary

Objective 103.8 tests operational editing competence. You do not need advanced plugin workflows, but you should be quick with modal editing, search/replace, and save/quit recovery sequences under time pressure.

### Possible Exam Questions

1. Which vi mode is used to enter text?
2. How do you save and quit in one command?
3. What command undoes the last change?
4. How do you replace all occurrences in the current file?

---

## Study Tip for Weighting

Because **103.1**, **103.3**, **103.4**, and **103.5** carry the highest weight, prioritize hands-on practice for:

- shell navigation and quoting,
- filesystem operations and archives,
- redirection/pipeline construction,
- process inspection and signaling.

Then reinforce regex and vi practice for speed and exam confidence.
