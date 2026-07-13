# OverTheWire – Bandit Level 9

**Date:** 2026-07-13

**Category:** Linux  

**Difficulty:** Medium

## Challenge Description

Find the password for the next level. It is stored in `data.txt`, a binary file containing human-readable strings. The password is preceded by several `=` characters.

## Approach

1. Connected to the Bandit server using the password obtained from Level 8.
2. Verified the presence of `data.txt`.
3. Used the `strings` utility to extract printable text from the binary file.
4. Piped the output to `grep` to filter lines containing multiple `=` characters.
5. Retrieved the password from the matching output.

## Commands Used

```bash
ssh bandit9@bandit.labs.overthewire.org -p 2220

# Password:
EjmOSvuAu7sGAHqHVcBDPirRe9T03kxl

strings data.txt | grep "==="
```

## Solution

The password for **Bandit Level 10** is:

```
B0s2khmbT9u0geKuOoVGW3JZKhndE3BG
```

## Lessons Learned

- `strings` extracts printable character sequences from binary files, making it useful for inspecting executables and other non-text files.
- Piping (`|`) allows the output of one command to become the input of another, creating efficient command-line workflows.
- `grep` can quickly isolate relevant information from a larger stream of text using pattern matching.
- Combining `strings` with `grep` is a common technique in malware analysis, reverse engineering, and digital forensics to uncover embedded configuration data, URLs, credentials, or other human-readable artifacts.

## Next Steps

Use the recovered password to access **Bandit Level 10**.