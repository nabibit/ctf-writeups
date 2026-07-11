# OverTheWire – Bandit Level 7

**Date:** 2026-07-11  

**Category:** Linux  

**Difficulty:** Easy

## Challenge Description

Find the password for the next level. It is stored in the file `data.txt` next to the word `millionth`.

## Approach

1. Connected to the Bandit server using the password obtained from Level 6.
2. Listed the files in the home directory and located `data.txt`.
3. Used `grep` to search the file for the keyword `millionth`.
4. Retrieved the password from the matching line.

## Commands Used

```bash
ssh bandit7@bandit.labs.overthewire.org -p 2220

# Password:
Bmnnvf82KzQlfxgAI2d1zYbr1u9pr3E3

ls

grep millionth data.txt
```

## Solution

The password for **Bandit Level 8** is:

```
VR1ljMayciFxbnUokuQmJFw6QC9VKtub
```

## Lessons Learned

- `grep` is one of the most useful Linux text-processing utilities for searching files.
- By default, `grep` prints the entire line containing the matching pattern.
- Searching for a unique keyword is much faster and more efficient than manually inspecting large text files.
- `grep` is widely used in system administration, log analysis, incident response, and digital forensics to quickly locate relevant information.

## Next Steps

Use the recovered password to access **Bandit Level 8**.