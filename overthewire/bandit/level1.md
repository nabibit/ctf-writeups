# OverTheWire – Bandit Level 1

**Date:** 2026-06-26

**Category:** Linux

**Difficulty:** Easy

## Challenge Description
Find the password for the next level, stored in a file named `-` (dash) in the home directory.

## Approach
1. Connected to the server using SSH with the password from Level 0.
2. Listed files using `ls` – found a file named `-`.
3. Attempted `cat -` – this didn't work because `-` is interpreted as standard input.
4. Used `cat ./-` to explicitly reference the file in the current directory.
5. Retrieved the password.

## Commands Used
```bash
ssh bandit1@bandit.labs.overthewire.org -p 2220
# password: 6y2kwnwK6grgvwvpvLaa2T1cpFEKOhNR
ls
cat ./-
```

## Solution
The password for Level 2 is: 
```
PK8fYLZg2hnHSz83plBL1iEPKdD3QToB
```

## Lessons Learned
Files can have unusual names like - (dash).

cat interprets - as standard input unless you provide a path (like ./-).

Always use ./ to reference files in the current directory when the name is ambiguous.

---