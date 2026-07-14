# OverTheWire – Bandit Level 10

**Date:** 2026-07-14

**Category:** Linux  

**Difficulty:** Easy

## Challenge Description

Find the password for the next level. It is stored in `data.txt`, which contains Base64-encoded data.

## Approach

1. Connected to the Bandit server using the password obtained from Level 9.
2. Listed the files in the home directory and located `data.txt`.
3. Used the `base64` utility with the `-d` option to decode the file contents.
4. Retrieved the decoded output, which contained the password for the next level.

## Commands Used

```bash
ssh bandit10@bandit.labs.overthewire.org -p 2220

# Password:
B0s2khmbT9u0geKuOoVGW3JZKhndE3BG

ls

base64 -d data.txt
```

## Solution

The password for **Bandit Level 11** is:

```
pYfOY6HwUsDj5rL9UvyhU7MCmv8vN5Ro
```

## Lessons Learned

- Base64 is an **encoding** scheme, not an encryption method; anyone can decode Base64-encoded data without a secret key.
- The `base64 -d` command decodes Base64-encoded input back to its original form.
- Base64 is commonly used to represent binary data as text in protocols and file formats such as email (MIME), JSON APIs, certificates, and configuration files.
- Recognizing common encoding formats is an important skill in system administration, digital forensics, and security analysis.

## Next Steps

Use the recovered password to access **Bandit Level 11**.