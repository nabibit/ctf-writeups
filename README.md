# CTF Write-ups

![CTF](https://img.shields.io/badge/CTF-Write--ups-blue)
![Linux](https://img.shields.io/badge/Linux-SSH_&_Commands-orange)
![Status](https://img.shields.io/badge/Status-Active-brightgreen)
![License](https://img.shields.io/badge/License-MIT-orange)

A collection of Capture The Flag (CTF) challenge write-ups, documenting my solutions, approaches, and lessons learned. This repository serves as both a personal knowledge base and a portfolio of my offensive security skills.

## Table of Contents

- [About](#about)
- [Repository Structure](#repository-structure)
- [Completed Challenges](#completed-challenges)
- [Write-up Template](#write-up-template)
- [Why This Matters](#why-this-matters)

## About

This repository contains detailed write-ups for CTF challenges I've completed across various platforms. Each write-up documents:

- The challenge description and goal.
- My thought process and approach.
- The exact commands and tools used.
- The solution (with sensitive flags redacted).
- Key lessons learned.

**Current Focus:** OverTheWire Bandit (Linux fundamentals, SSH, command-line tools).

---

## Repository Structure

```
ctf-writeups/
├── overthewire/
│   └── bandit/
│       ├── level0.md
│       ├── level1.md
│       ├── level2.md
│       ├── level3.md
│       ├── level4.md
│       ├── level5.md
│       ├── level6.md
│       ├── level7.md
│       ├── level8.md
│       ├── level9.md
│       ├── level10.md
│       ├── level11.md
│       ├── level12.md
│       ├── level13.md
│       ├── level14.md
│       └── ...
└── README.md
```

Each file is a self-contained markdown document following a consistent template.

---

## Completed Challenges

### OverTheWire – Bandit (0–14)

| Level | Difficulty | Key Skills | Status |
|-------|------------|------------|--------|
| 0 | Easy | SSH, `cat` | ✅ |
| 1 | Easy | `cat ./-` | ✅ |
| 2 | Easy | Spaces in filenames, quotes | ✅ |
| 3 | Easy | Hidden files (`ls -la`) | ✅ |
| 4 | Easy | `file` command, ASCII detection | ✅ |
| 5 | Easy–Medium | `find -size -executable` | ✅ |
| 6 | Medium | `find -user -group -size` | ✅ |
| 7 | Easy | `grep` | ✅ |
| 8 | Medium | `sort`, `uniq -u` | ✅ |
| 9 | Medium | `strings`, `grep ===` | ✅ |
| 10 | Easy | `base64 -d` | ✅ |
| 11 | Easy | `tr` ROT13 decryption | ✅ |
| 12 | Medium | `xxd -r`, nested compression | ✅ |
| 13 | Easy–Medium | SSH private key authentication | ✅ |
| 14 | Easy | `nc` (netcat) | ✅ |
| 15+ | ... | ... | ⏳ In Progress |

---

## Write-up Template

Each write-up follows a consistent structure:

```markdown
# OverTheWire – Bandit Level X

**Date:** YYYY-MM-DD

**Category:** Linux / [Tool]

**Difficulty:** Easy / Medium / Hard

## Challenge Description
[What is the goal?]

## Approach
[Step-by-step reasoning and execution.]

## Commands Used

```bash
# Commands here


## Solution

The password for Level X+1 is: `[FLAG]`

## Lessons Learned

- [Key takeaway 1]
- [Key takeaway 2]

## Next Steps

[What to do next]
```

---

## Why This Matters

Documenting CTF challenges is more than just "saving the answer." It's about:

1. **Reinforcing learning:** Writing the explanation forces me to truly understand the concept.
2. **Building a reference:** I can quickly revisit techniques (e.g., `xxd -r`, `file` commands, SSH keys).
3. **Portfolio visibility:** Recruiters see not just that I solved challenges, but *how* I think and approach problems.

---

## Next Steps

- Continue through Bandit levels 15+.
- Expand to other CTF platforms (TryHackMe, HackTheBox, etc.).
- Add more detailed sections (e.g., "Alternative approaches", "Common pitfalls").

---

## Acknowledgements

Built while practicing on [OverTheWire](https://overthewire.org/wargames/bandit/) and learning Linux fundamentals.

---