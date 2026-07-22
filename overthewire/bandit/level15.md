# OverTheWire – Bandit Level 15

**Date:** 2026-07-22

**Category:** Linux / Networking / SSL/TLS

**Difficulty:** Easy

## Challenge Description

Find the password for Level 16 by submitting the current password to a service running on `localhost` port 30001 **using SSL/TLS encryption**.

## Approach

1. Connected to the server as `bandit15` using the password obtained from Level 14 (`pbLYuZtTg4MgaqfJx8jbA9gKKGqM68A7`).
2. Used `openssl s_client` to establish a secure connection to `localhost` on port 30001.
3. Submitted the current password (`/etc/bandit_pass/bandit15`).
4. The service responded with the password for Level 16.

## Commands Used

```bash
openssl s_client -connect localhost:30001
# pbLYuZtTg4MgaqfJx8jbA9gKKGqM68A7
```

## Solution
The password for Level 16 is:
kS0Hf0u5HiXFwKMKFqXvPdOTNGGa0X8V

## Lessons Learned
- `openssl s_client` is the tool for connecting to SSL/TLS encrypted services.
- Many services require encryption to protect data in transit.
- Port 30001 is commonly used for secure custom services.

## Next Steps
Proceed to Level 16 using the retrieved password.