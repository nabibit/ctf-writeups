# OverTheWire – Bandit Level 14

**Date:** 2026-07-21

**Category:** Linux / Networking

**Difficulty:** Easy

## Challenge Description
Find the password for Level 15, by submitting the current password to a service running on `localhost` port 30000.

## Approach
1. Connected to the server as `bandit14` using the password from Level 13.
2. Used `nc` (netcat) to connect to `localhost` on port 30000.
3. Submitted the current password (`/etc/bandit_pass/bandit14`).
4. Received the password for Level 15.

## Commands Used

```bash
nc localhost 30000
# aaWecNkG4FhxJQxz07uiwzVP6bJiYS65
```

## Solution

The password for Level 15 is: pbLYuZtTg4MgaqfJx8jbA9gKKGqM68A7

## Lessons Learned

- `nc` (netcat) can connect to TCP ports and send/receive data.
- Useful for interacting with simple network services.
- Port 30000 is a common port for custom services.

## Next Steps

Proceed to Level 15 using the retrieved password.
