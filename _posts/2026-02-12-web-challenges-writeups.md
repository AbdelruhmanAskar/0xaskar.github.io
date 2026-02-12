---
layout: single
title: "N!ghtM4re CTF 2026: WEB Challenges Writeups"
date: 2026-02-12
categories: [Writeups, WEB]
tags: [CTF, WEB , Author]
author_profile: true
---

# 🕸️ WEB Series: The Author's Writeups

Hello everyone!

This post marks a new chapter in my journey. After dominating the OSINT field,
I decided to dive deep into the Web Exploitation realm—but this time, as the Architect.

For N!ghtM4re CTF, I stepped into the role of a Challenge Author to design environments that test not just your tools,
but your fundamental understanding of how the web breathes 🥳🥳

---

## 🚩 1. Challenge Write-up: Bl1nd Fa1th
=========================================

### 🛠️ General Information

*   **Challenge Name:** Bl1nd Fa1th
    
*   **Difficulty:** Basic
    
*   **Points:** 50
    
*   **Author:** D3xter
    
* * *

### 📜 The Description

> _"There is a rule in place. It was never written. It was never questioned."_

![Challenge Photo](https://raw.githubusercontent.com/AbdelruhmanAskar/0/refs/heads/master/assets/images/Bl1nd%20Fa1th/Challenge.png)

* * *

### 🔍 Stage 1: The Hidden Whisper (Reconnaissance)

Upon landing on the challenge page, I was greeted by a standard **Login** interface. No obvious hints, no flashy clues.

![Login Page](https://raw.githubusercontent.com/AbdelruhmanAskar/0/refs/heads/master/assets/images/Bl1nd%20Fa1th/Login.png)

But a true researcher knows that the best secrets are often hidden in plain sight.

I performed an **`Inspect Element`** to dive into the source code. Nestled within the comments, I found a developer's note left behind: \`\`

**Bingo.** The first piece of the puzzle:

*   **Target Username:** `@dmindex021`

![Inspect](https://raw.githubusercontent.com/AbdelruhmanAskar/0/refs/heads/master/assets/images/Bl1nd%20Fa1th/Inspect.png)

* * *

### 🔓 Stage 2: Breaking the Logic (Exploitation)

Now I had the identity, but the password was still a black box. Instead of guessing or brute-forcing,

I decided to attack the underlying logic of the database.

I opted for a classic **SQL Injection (SQLi)** bypass. By injecting a logical tautology into the password field,

I could trick the server into validating the login regardless of the actual password.

*   **Input Payload:** `1' or 1=1--`
    

**The Breakdown:**

*   The `'` closes the original string.
    
*   The `or 1=1` creates a condition that is always **True**.
    
*   The `--` (comment) tells the database to ignore the rest of the original query.
    

* * *

### 🏆 Stage 3: System Access (The Flag)

The moment I hit **Login**, the system's defenses crumbled. The terminal screen flickered to life, granting me full access:

![Flag](https://raw.githubusercontent.com/AbdelruhmanAskar/0/refs/heads/master/assets/images/Bl1nd%20Fa1th/flag.png)

Plaintext

    AUTHENTICATED_SESSION
    ACCESS GRANTED
    [ ACTIVE_TERMINAL_SESSION ]
    > FLAG: N!ghtM4re{5ql_15_n0t_4_8u6_1t5_4_f34tur3!!}
    SESSION_STATE: STABLE 

**The Flag:** `N!ghtM4re{5ql_15_n0t_4_8u6_1t5_4_f34tur3!!}`
