# OverTheWire – Bandit Level 3

**Date:** 2026-07-08  

**Category:** Linux  

**Difficulty:** Easy

## Challenge Description

Find the password for the next level, stored in a hidden file located inside the `inhere` directory.

## Approach

1. Connected to the target server via SSH using the credentials obtained in Level 2.
2. Listed the directory contents using `ls` and located the `inhere` directory.
3. Navigated into the directory (`cd inhere`) and executed `ls -la` to reveal hidden entries.
4. Identified a hidden file named `...Hiding-From-You` (prefixed with three dots).
5. Retrieved the Level 4 password using `cat`, ensuring the filename was entered exactly.

## Commands Used

```
ssh bandit3@bandit.labs.overthewire.org -p 2220

# Password for Level 3
7ZZ2LFrykP2zEyvBl4m3clcL7tGYJPME

ls
cd inhere
ls -la
cat ...Hiding-From-You
exit
```

## Solution

The password for Level 4 is:

`xzTXq1rDJQVVAzdv5cHq1TQytTWufAMq`

## Lessons Learned

- In UNIX-like operating systems, files beginning with a dot (`.`) are hidden from the default `ls` output.
- Using `ls -la` is essential during security investigations and system administration to reveal hidden files and inspect permissions.
- Hidden filenames are not limited to a single leading dot—names such as `...Hiding-From-You` are perfectly valid and require precise typing or Tab completion.

## Next Steps

Proceed to Bandit Level 4 using the retrieved password.