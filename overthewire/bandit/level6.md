# OverTheWire – Bandit Level 6

**Date:** 2026-07-10  

**Category:** Linux  

**Difficulty:** Medium

## Challenge Description

Find the password for the next level. It is stored **somewhere on the server** in a file that meets all of the following criteria:

- Owned by user **bandit7**
- Owned by group **bandit6**
- Exactly **33 bytes** in size

## Approach

1. Connected to the Bandit server using the password obtained from Level 5.
2. Searched the entire filesystem starting from the root directory (`/`).
3. Used the `find` command with filters for file owner, group, and file size.
4. Redirected permission errors to `/dev/null` to keep the output clean.
5. Located the matching file at `/var/lib/dpkg/info/bandit7.password`.
6. Displayed its contents using `cat` to retrieve the password for the next level.

## Commands Used

```bash
ssh bandit6@bandit.labs.overthewire.org -p 2220

# Password: 
pXa26xhMWaC2SvDotA4r9EgZkulOeSBW

find / -user bandit7 -group bandit6 -size 33c 2>/dev/null

cat /var/lib/dpkg/info/bandit7.password
```

## Solution

The password for **Bandit Level 7** is:

```
Bmnnvf82KzQlfxgAI2d1zYbr1u9pr3E3
```

## Lessons Learned

- The `find` command can search the entire filesystem while combining multiple search predicates.
- `-user` filters files owned by a specific user.
- `-group` filters files belonging to a specific group.
- `-size 33c` searches for files that are exactly **33 bytes** (`c` specifies bytes).
- Redirecting standard error with `2>/dev/null` suppresses permission-denied messages, making search results easier to read during system administration and forensic investigations.

## Next Steps

Use the recovered password to access **Bandit Level 7**.