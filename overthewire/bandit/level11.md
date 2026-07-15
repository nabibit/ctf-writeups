# OverTheWire – Bandit Level 11

**Date:** 2026-07-15 

**Category:** Linux  

**Difficulty:** Easy

## Challenge Description

Find the password for the next level. It is stored in `data.txt`, where every alphabetical character has been rotated by 13 positions using the ROT13 cipher.

## Approach

1. Connected to the Bandit server using the password obtained from Level 10.
2. Listed the files in the home directory and located `data.txt`.
3. Used the `tr` command to apply the ROT13 transformation by translating each letter to its corresponding rotated character.
4. Retrieved the decoded output, which contained the password for the next level.

## Commands Used

```bash
ssh bandit11@bandit.labs.overthewire.org -p 2220

# Password:
pYfOY6HwUsDj5rL9UvyhU7MCmv8vN5Ro

ls

cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

## Solution

The password for **Bandit Level 12** is:

```
GROozWPO8QyN0mGrjUkID0WCYkZiQxrN
```

## Lessons Learned

- ROT13 is a Caesar cipher that rotates each letter by **13 positions** in the alphabet.
- Since the English alphabet contains 26 letters, applying ROT13 **twice** restores the original text.
- The `tr` command performs character-by-character translation, making it well suited for simple substitution ciphers such as ROT13.
- Text transformation tools like `tr` are useful in shell scripting, log processing, and decoding simple encoded data during security investigations.

## Next Steps

Use the recovered password to access **Bandit Level 12**.