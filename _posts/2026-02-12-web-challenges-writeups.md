---
layout: single
title: "N!ghtM4re CTF 2026: Web Challenges Writeups"
date: 2026-02-12
categories: [Writeups, WEB]
tags: [CTF, WEB , Author]
author_profile: true
---

# 🕸️ Web Writeups

Hello everyone!

Hello everyone! I’m really excited to share this post with you all. This time, things are a bit different! For the first time ever, I’ve stepped into the shoes of a Web Challenge Author for N!ghtM4re CTF 2026 🥳🥳.

It’s been an incredible experience moving from the "solver" side to the "architect" side. Designing these challenges was a lot of fun—thinking about how to hide the flags and creating tricky paths for the players really opened my eyes to how the web works from the inside out. I'm honestly so happy with how they turned out and seeing everyone's creative solutions was the best part of the journey.

In this post, I’ll be breaking down web challenges, ranging from Basic to Hard. Whether you're a beginner or a pro, I hope you find these writeups helpful and enjoy the logic behind them!

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

I performed an **`Inspect Element`** to dive into the source code. Nestled within the comments, I found a developer's note left behind.

![Inspect](https://raw.githubusercontent.com/AbdelruhmanAskar/0/refs/heads/master/assets/images/Bl1nd%20Fa1th/Inspect.png)

The first piece of the puzzle:

*   **Target Username:** `@dmindex021`

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

The moment I hit **Login**, the system's defenses crumbled, granting me full access:

![Flag](https://raw.githubusercontent.com/AbdelruhmanAskar/0/refs/heads/master/assets/images/Bl1nd%20Fa1th/flag.png)


**The Flag:** `N!ghtM4re{5ql_15_n0t_4_8u6_1t5_4_f34tur3!!}`

---

## 🚩 2. Challenge Write-up: SODA3
=========================================
### 🛠️ General Information
*   **Challenge Name:** SODA3
    
*   **Difficulty:** Easy
    
*   **Author:** Kud0x1
    
![Challenge](https://raw.githubusercontent.com/AbdelruhmanAskar/0/refs/heads/master/assets/images/Soda3/SODA3%20Challenge.png)
    
* * *
### 📜 The Description
> _"When nothing remains, everything becomes possible."_
The challenge presents us with an **"Internal File Manager."** It seems simple: you can create files, view them, or reset the environment. But as we know, the most straightforward paths often have the most interesting locks.

![File Manager](https://raw.githubusercontent.com/AbdelruhmanAskar/0/refs/heads/master/assets/images/Soda3/File%20Manager.png)
* * *

### 🔍 Stage 1: The Gatekeeper (Reconnaissance)
Upon entering the challenge, I saw a dashboard with a few options: **Create**, **Files**, and a **Reset** button. There was already a file named `flag` sitting there, but clicking it led to a dead end:
> **Response:** You have to reset the files first!

![Reset Error](https://raw.githubusercontent.com/AbdelruhmanAskar/0/refs/heads/master/assets/images/Soda3/Reset%20Flags.png)
Naturally, I tried to hit the **Reset** button. I intercepted the request in **Burp Suite** to see what was happening under the hood.

* * *

### 🚧 Stage 2: The Blocked Path (Method Not Allowed)
The application was sending a `POST` request to `/reset`. However, the server responded with a cold:
`HTTP/1.1 405 METHOD NOT ALLOWED`

![Burp Request](https://raw.githubusercontent.com/AbdelruhmanAskar/0/refs/heads/master/assets/images/Soda3/burp%20request.png)

Looking at the `Allow` header in the response, the server dropped a huge hint:
`Allow: HEAD, OPTIONS`

The standard `POST` method was disabled for resetting, but the server was still listening for **HEAD** requests.
* * *

### 🔓 Stage 3: The HEAD Trick (Exploitation)
A **HEAD** request is identical to a `GET` request, but the server returns only the headers and no body. Sometimes, developers forget to apply the same security restrictions to `HEAD` as they do to `POST` or `GET`.
I decided to bypass the restriction using **cURL** to force a `HEAD` request to the reset endpoint:

curl -X HEAD [http://nightmare.offgrayeg.com](http://nightmare.offgrayeg.com):7878/reset

![Curl Reset](https://raw.githubusercontent.com/AbdelruhmanAskar/0/refs/heads/master/assets/images/Soda3/Curl%20Reset.png)

The command executed successfully. Even though I didn't see a "Success" message (because HEAD doesn't return a body), the server-side logic was triggered, and the files were reset!
* * *

🏆 Stage 4: Capturing the Flag
Now that the "Reset" condition was satisfied, I went straight for the gold. I requested the flag file again using a simple GET request:

bash
curl [http://nightmare.offgrayeg.com](http://nightmare.offgrayeg.com):7878/flag

![Flag](https://raw.githubusercontent.com/AbdelruhmanAskar/0/refs/heads/master/assets/images/Soda3/Flag.png)

The Flag: N!ghtM4re{H34D_Req_Ar3_N0t_Alw4ys_S4f3!!}
