# OverTheWire – Bandit Level 8

**Date:** 2026-07-12  

**Category:** Linux  

**Difficulty:** Medium

## Challenge Description

Find the password for the next level. It is stored in `data.txt` and is the **only line that appears exactly once**.

## Approach

1. Connected to the Bandit server using the password obtained from Level 7.
2. Verified the presence of `data.txt`.
3. Used `sort` to arrange all lines in alphabetical order.
4. Piped the sorted output to `uniq -u` to display only lines that occur exactly once.
5. Retrieved the unique line, which contained the password for the next level.

## Commands Used

```bash
ssh bandit8@bandit.labs.overthewire.org -p 2220

# Password:
VR1ljMayciFxbnUokuQmJFw6QC9VKtub

sort data.txt | uniq -u
```

## Solution

The password for **Bandit Level 9** is:

```
EjmOSvuAu7sGAHqHVcBDPirRe9T03kxl
```

## Lessons Learned

- `uniq` compares **adjacent** lines, so input should be sorted first.
- `sort` groups identical lines together, allowing `uniq -u` to identify lines that appear exactly once.
- Unix pipelines (`|`) enable simple utilities to be combined into powerful data-processing workflows.
- Commands like `sort` and `uniq` are commonly used for log analysis, data deduplication, and processing large text datasets.

## Next Steps

Use the recovered password to access **Bandit Level 9**.