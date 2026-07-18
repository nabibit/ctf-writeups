# OverTheWire – Bandit Level 13

**Date:** 2026-07-18

**Category:** Linux / SSH

**Difficulty:** Easy–Medium

## Challenge Description
Find the password for Level 14, stored in `/etc/bandit_pass/bandit14`. An SSH private key (`sshkey.private`) is provided to log in as `bandit14`.

## Approach
1. Connected to the server as `bandit13` using the password from Level 12.
2. Listed files – found `sshkey.private`.
3. Attempted to connect from within the `bandit13` session to `bandit14@localhost` – this failed because the server blocks SSH connections from localhost to conserve resources.
4. Copied the private key to my local machine using `scp` to bypass the restriction.
5. Used the key to connect directly to `bandit14@bandit.labs.overthewire.org` from my local machine.
6. Read the password file.

## Troubleshooting
- **"Connecting from localhost is blocked"** – this occurred when trying to SSH to `localhost` from within the `bandit13` session. The server intentionally blocks localhost connections.
- **Typo in `UserKnownHostsFIle`** – I initially typed `UserKnownHostsFIle` (capital `I` instead of `F`), causing the option to be ignored and the SSH client to fall back to password authentication. The correct flag is `UserKnownHostsFile`.
- **The fix:** Copy the private key to the local machine with `scp`, set correct permissions (`chmod 600`), and connect externally.

## Commands Used
```bash
# From the bandit13 session (the key is already there):
bandit13@bandit:~$ ls -la
# Output: sshkey.private is visible

# From my local machine (after exiting bandit13):
scp -P 2220 bandit13@bandit.labs.overthewire.org:sshkey.private .
chmod 600 sshkey.private
ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220

# Once logged in as bandit14:
cat /etc/bandit_pass/bandit14
```

## Solution
The password for Level 14 is: 
aaWecNkG4FhxJQxz07uiwzVP6bJiYS65

## Lessons Learned
- SSH private keys can be used to authenticate without a password.
- The `-i` option specifies an identity file.
- `scp` can copy files between remote and local machines over SSH.
- Localhost connections on the OverTheWire servers are often restricted; you must connect externally.
- Attention to detail matters – a single typo in an option (`UserKnownHostsFIle` vs `UserKnownHostsFile`) can cause authentication failures.
- Always set `chmod 600` on private keys – SSH will refuse to use them if permissions are too open.

## Next Steps

Proceed to Level 14 using the retrieved password.