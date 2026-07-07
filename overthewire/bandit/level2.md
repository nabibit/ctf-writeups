# OverTheWire – Bandit Level 2

**Date:** 2026-07-07  

**Category:** Linux  

**Difficulty:** Easy

## Challenge Description

Find the password for the next level, stored in a file with spaces in its name located in the home directory.

## Approach

1. Connected to the target server via SSH using the credentials obtained in Level 1.
2. Listed directory contents using `ls -la` and identified a file named `spaces in this filename`.
3. Bypassed standard bash word-splitting by enclosing the filename in double quotes.
4. Extracted the plaintext password for Level 3.

## Commands Used

```
ssh bandit2@bandit.labs.overthewire.org -p 2220

# Password for Level 2
PK8fYLZg2hnHSz83plBL1iEPKdD3QToB

ls

cat ".\--spaces in this filename--"
```

## Solution

The password for Level 3 is:

`7ZZ2LFrykP2zEyvBl4m3clcL7tGYJPME`

## Lessons Learned

- Unquoted spaces in Bash act as command argument delimiters, causing commands like `cat` to interpret each word as a separate filename.
- To handle filenames containing spaces, enclose the path in quotes (`"file name"`).

## Next Steps

Proceed to Bandit Level 3 using the retrieved password.