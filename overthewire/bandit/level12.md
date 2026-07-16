# OverTheWire – Bandit Level 12

**Date:** 2026-07-16 

**Category:** Linux / Forensics  

**Difficulty:** Medium

## Challenge Description

Find the password for the next level, stored in `data.txt`, which contains a hexdump of a file that has been compressed multiple times using different archive formats.

## Approach

1. Connected to the target server via SSH using the credentials obtained in Level 11.
2. Created a temporary working directory under `/tmp` to safely manipulate files.
3. Copied `data.txt` into the workspace and reversed the hexdump using `xxd -r`.
4. Used the `file` utility after each extraction step to identify the next compression or archive format.
5. Repeatedly decompressed and extracted the nested payloads (`gzip`, `bzip2`, and `tar`) until an ASCII text file was revealed.
6. Read the final text file to obtain the Level 13 password.

## Commands Used

```bash
ssh bandit12@bandit.labs.overthewire.org -p 2220
# password: 
GROozWPO8QyN0mGrjUkID0WCYkZiQxrN

mkdir /tmp/bandit12
cp data.txt /tmp/bandit12/
cd /tmp/bandit12

# Reverse hexdump
xxd -r data.txt > file

# Decompression chain
file file
mv file file.gz
gunzip file.gz

file file
mv file file.bz2
bunzip2 file.bz2

file file
mv file file.gz
gunzip file.gz

file file
tar -xvf file

file data5.bin
tar -xvf data5.bin

file data6.bin
mv data6.bin data6.bin.bz2
bunzip2 data6.bin.bz2

file data6.bin
tar -xvf data6.bin

file data8.bin
mv data8.bin data8.bin.gz
gunzip data8.bin.gz

file data8.bin
cat data8.bin
```

## Solution

The password for Level 13 is:

qQYQiHOBPR8zR61qxYqX45quvihF2uzk

## Lessons Learned

* `xxd -r` reconstructs binary files from hexadecimal dumps.
* The `file` command is invaluable for identifying unknown file formats and choosing the correct extraction tool.
* Real-world forensic investigations often involve multiple layers of compression and archival formats.
* Archive and compression technologies serve different purposes: `tar` bundles files together, while `gzip` and `bzip2` compress data.
* A systematic workflow of **identify → extract → identify again** prevents mistakes when dealing with nested payloads.

## Next Steps

Proceed to Level 13 using the retrieved password.