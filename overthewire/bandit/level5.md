# OverTheWire – Bandit Level 5

**Date:** 2026-07-09

**Category:** Linux  

**Difficulty:** Easy–Medium

## Challenge Description

Find the password for the next level. It is stored in a file that is **human-readable**, exactly **1033 bytes** in size, and **not executable**.

## Approach

1. Connected to the Bandit server using the password obtained from Level 4.
2. Listed the contents of the home directory and located the `inhere` directory.
3. Changed into `inhere`.
4. Used the `find` command to search recursively for files matching the required criteria:
   - Regular file (`-type f`)
   - Exactly 1033 bytes (`-size 1033c`)
   - Not executable (`! -executable`)
5. Identified the matching file at `./maybehere07/.file2`.
6. Displayed its contents using `cat` to retrieve the password for the next level.

## Commands Used

```bash
ssh bandit5@bandit.labs.overthewire.org -p 2220

# Password:
6C7h9GD8M6ai5nr7wo1RonrzFjj9yIrG

ls
cd inhere

find . -type f -size 1033c ! -executable

cat ./maybehere07/.file2
```

## Solution

The password for **Bandit Level 6** is:

```
pXa26xhMWaC2SvDotA4r9EgZkulOeSBW
```

## Lessons Learned

- The `find` utility can efficiently search large directory trees using multiple filtering criteria.
- `-type f` restricts the search to regular files.
- `-size 1033c` searches for files that are exactly **1033 bytes** (`c` denotes bytes).
- `! -executable` excludes files with executable permissions, making it easy to narrow down the search.
- Combining several predicates into a single `find` command is a common and efficient technique in Linux system administration and forensic investigations.

## Next Steps

Use the recovered password to access **Bandit Level 6**.