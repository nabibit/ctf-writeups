# OverTheWire – Bandit Level 4

**Date:** 2026-07-09  

**Category:** Linux 

**Difficulty:** Easy

## Challenge Description

Find the password for the next level. It is stored in the only human-readable file inside the `inhere` directory.

## Approach

1. Connected to the Bandit server using the password obtained from Level 3.
2. Entered the `inhere` directory.
3. Used the `file` command on every file simultaneously to determine each file's actual type.
4. Identified `-file07` as the only ASCII text file.
5. Displayed its contents using `cat` with a relative path to avoid interpreting the filename as a command-line option.

## Commands Used

```bash
ssh bandit4@bandit.labs.overthewire.org -p 2220

# Password:
xzTXq1rDJQVVAzdv5cHq1TQytTWufAMq

cd inhere

file ./*-file*

cat ./-file07
```

## Solution

The password for **Bandit Level 5** is:

```
6C7h9GD8M6ai5nr7wo1RonrzFjj9yIrG
```

## Lessons Learned

- The `file` utility determines a file's actual format by inspecting its contents rather than relying on its filename.
- Files beginning with `-` should be referenced using a relative path such as `./filename` so they are not interpreted as command-line options.
- This technique is commonly used during forensic investigations and malware analysis when filenames cannot be trusted.

## Next Steps

Use the recovered password to access Bandit Level 5.