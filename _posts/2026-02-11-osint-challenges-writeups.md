---
layout: single
title: "N!ghtM4re CTF 2026: OSINT Challenges Writeups"
date: 2026-02-10
categories: [Writeups, OSINT]
tags: [CTF, OSINT, Investigation, CyberCrime, Author]
author_profile: true
---

# 🕵️‍♂️ OSINT Series: The Author's Writeups

Hello everyone! 

This post is a special milestone in my journey. For the first time, I stepped away from the player's seat and took on the role of an **OSINT Challenge Author** for **N!ghtM4re CTF**🥳🥳.

Designing these challenges was an incredible experience—moving from solving puzzles to crafting them requires a different perspective. I wanted to create scenarios that feel real, blending deep-web investigation with real-world criminal profiling. I’m thrilled with the feedback from the participants and seeing the creative ways they approached my challenges.

Below are the writeups for the 3 OSINT challenges I designed, ordered from **Easy to Hard**.

---

## 1. The Royal Neighbor (Easy)

## **📝 The Challenge Description**

![Challenge Photo](https://raw.githubusercontent.com/AbdelruhmanAskar/0/refs/heads/master/assets/images/A%20Royal%20Neighbor/The%20Royal%20Neighbor.png)

> "I was wandering around this academic building when I decided to take a break. Just a few steps away, I entered a nearby garden and stumbled upon a fountain featuring a dragon's head. It looked quite familiar, almost like it was designed by a legendary architect who shaped the whole city.
> 
> I took a photo of the faculty building before I left. Can you find the name of that hidden dragon fountain?"
> 
> **Flag Format:** `N!ghtM4re{Name_of_the_fountain}`
> 
> **Note on Flag Sensitivity:** Accuracy is key! The name of the fountain must be written with the correct Catalan accents and specific casing. Note the difference between a standard **"e"** and the accented **"é"**.
> 
> **How to format the name:** To help you format the name correctly, here are two examples using different names to show how special characters, casing, and accents work:
> 
> *   **Example 1 (Apostrophe & Casing):** If the answer was _Joan d'Alacant_, the flag would be: `N!ghtM4re{Joan_d'Alacant}` (Note the small `d` and capital `A`).
> *   **Example 2 (Accents):** If the answer was _Castell de Mercè_, the flag would be: `N!ghtM4re{Castell_de_Mercè}` (Note the `è` instead of `e`).

![Challenge Photo](https://raw.githubusercontent.com/AbdelruhmanAskar/0xaskar.github.io/refs/heads/master/assets/images/A%20Royal%20Neighbor/Place.png)

* * *

### 🔍 Phase 1: Visual Identification

The investigation began with the challenge photo of a modern, academic-looking building.

**Analysis:** I performed a **Reverse Image Search** (using Google Lens/Yandex) on the faculty building photo.

![Facility](https://raw.githubusercontent.com/AbdelruhmanAskar/0xaskar.github.io/refs/heads/master/assets/images/A%20Royal%20Neighbor/Facility.png)

**The Breakthrough:** The search results immediately identified the building as the **Facultat de Dret (Faculty of Law)** at the **University of Barcelona (UB)** in Barcelona, Spain. The unique architectural lines and the specific mural on the building are iconic to this campus located on _Avinguda Diagonal_.

* * *

### 🌳 Phase 2: Locating the "Royal" Break Spot

The challenge description provided a narrative clue:

> _"Just a few steps away, I entered a nearby garden and stumbled upon a fountain featuring a dragon's head."_

**Mapping the Area:** By checking satellite imagery and maps around the **Facultat de Dret**, I noticed a large green space directly adjacent to the university grounds: **Jardins de Pedralbes** (the gardens of the Royal Palace of Pedralbes).

![Fountain](https://raw.githubusercontent.com/AbdelruhmanAskar/0xaskar.github.io/refs/heads/master/assets/images/A%20Royal%20Neighbor/Fountain.png)

* * *

### 🐉 Phase 3: The Legendary Architect's Work

The description mentioned a fountain with a **dragon's head** designed by a **legendary architect** who "shaped the whole city."

**Investigation:**

1.  Barcelona's most legendary architect is undoubtedly **Antoni Gaudí**.
2.  I searched for "dragon fountain"
3.  I discovered the **Font d'Hèrcules** (Hercules Fountain).

**Historical Context:** This fountain features a wrought-iron dragon’s head as a spout. Interestingly, it was overlooked for years and "hidden" by overgrown vegetation until it was restored and rediscovered in the 1980s, matching the challenge's lore perfectly.

* * *

**Final Flag:**`N!ghtM4re{Font_d'Hércules}`

==============================================

## 2. A Weird Challenge (Medium)

## 📝 The Challenge Description

![Challenge Photo](https://raw.githubusercontent.com/AbdelruhmanAskar/0/refs/heads/master/assets/images/A%20Weird%20Combo%20WriteUp/A%20Weird%20Combo.png)

> "I took this photo right before hopping on the metro. I was starving, so I only rode for one station and got off. The station I arrived at made me feel like I was protected from the rain, even though the sun was shining!
> 
> Just a few steps away from the exit, I found a restaurant with a very weird menu. Who would have thought you could order Liver and Brains along with a Crepe from the same place?! The name is a bit of a mouthful, but the spot is iconic.
> 
> I saved their phone number from the Google Maps. Can you find it?"

**The Original Challenge Photo:**
![Original Challenge Photo](https://raw.githubusercontent.com/AbdelruhmanAskar/0xaskar.github.io/refs/heads/master/assets/images/A%20Weird%20Combo%20WriteUp/Original%20Challenge%20Photo.jpg)

**Flag Format:** `N!ghtM4re{Restaurant Phone Number}`

---

## 🔍 Step 1: Where did we start?

First, I had a photo of a metro station. I used **Google Reverse Image Search** and added the keyword "Metro" to help the search engine.

![Reverse Search Result](https://raw.githubusercontent.com/AbdelruhmanAskar/0xaskar.github.io/refs/heads/master/assets/images/A%20Weird%20Combo%20WriteUp/reverse-image.png)

The search confirmed that the starting point is **Kolleyet El-Zeraa Station** (Faculty of Agriculture). 

---

## 🚇 Step 2: One station away... but where?

The description says: *"I only rode for one station and got off."*

I checked the official [Cairo Metro website](https://www.cairometro.gov.eg/ar/stations/20?information=1) to see the map. From Kolleyet El-Zeraa, riding for one station leads to only two possibilities:
1. **Shobra El-Kheima Station**
2. **Mazallat Station**

![Metro Map](https://raw.githubusercontent.com/AbdelruhmanAskar/0xaskar.github.io/refs/heads/master/assets/images/A%20Weird%20Combo%20WriteUp/paths.png)

---

## 💡 Step 3: Solving the Riddle

Now, let's look at the hint: *"The station I arrived at made me feel like I was protected from the rain, even though the sun was shining!"*

What protects you from the rain? **Umbrellas!** ⛱️
In Arabic, "Umbrellas" means **"Mazallat" (مظلات)**. 

Bingo! The destination is **Mazallat Metro Station**.

---

## 🍔 Step 4: Finding the "Weird Combo"

The description mentioned a restaurant right outside the exit with a very strange menu: **Liver, Brains, and Crepes!** (Yes, a very weird combo indeed 😂).

I went to **Google Maps**, searched near Mazallat Station, and looked for restaurants.

![Google Maps Search](https://raw.githubusercontent.com/AbdelruhmanAskar/0xaskar.github.io/refs/heads/master/assets/images/A%20Weird%20Combo%20WriteUp/google-map.png)

I found it: **"Kebda w Mokh w Crepe El-Iman Asran" (كبدة ومخ وكريب الايمان عصران)**. The name is definitely a "mouthful"!

I checked the **"About"** section on Google Maps to find the phone number.

![Restaurant Phone Number](https://raw.githubusercontent.com/AbdelruhmanAskar/0xaskar.github.io/refs/heads/master/assets/images/A%20Weird%20Combo%20WriteUp/resturant.png)

---

## 🏁 The Flag

The phone number listed is `01111132001`.

**Final Flag:** `N!ghtM4re{01111132001}`

==============================================

## 3. Operation: Ghost in the Cage (Hard)

## 💀 The Challenge Description

![Challenge Photo](https://raw.githubusercontent.com/AbdelruhmanAskar/0/refs/heads/master/assets/images/Opeartion%20Ghost%20in%20the%20Cage/Opeartion%20Ghost%20in%20the%20Cage.png)

> "A high-ranking individual on the **FBI’s Cyber Most Wanted** list is known for operating one of the most sophisticated **Carding Shops** in the underground scene.
> This Russian national specialized in the large-scale theft and sale of financial access devices and stolen identities.
> He didn't just sell credentials; he managed a massive digital warehouse that bridged the gap between raw data and illegal profit. His operation was a primary source for cyber-criminals worldwide, providing the keys to thousands of private accounts and financial platforms."

**Criminal Profile:**

*   **Nationality:** Russian
    
*   **Specialization:** Managing a "Carding" enterprise and identity fraud.
    
*   **Status:** Fugitive. Known for hiding his true identity behind multiple layers of digital noise.
    

**Mission Objectives:**

1.  **Identify the Alias.**
    
2.  **Locate the Evidence:** Track down his development history.
    
3.  **The Extraction:** Find the final flag hidden inside a backup project.
    

* * *

### 🔍 Phase 1: Criminal Profiling & Reconnaissance

The investigation began by analyzing the key indicators provided in the description: **"FBI’s Cyber Most Wanted list"**, **"Carding Shops"**, and **"Russian National"**.

Using a targeted Google Dork, I filtered through the noise to find specific FBI indictments matching this profile:

**Search Query:** `intext:"FBI's Cyber Most Wanted list" "Carding Shops" "Russian"`

![Search Query](https://raw.githubusercontent.com/AbdelruhmanAskar/0xaskar.github.io/refs/heads/master/assets/images/Opeartion%20Ghost%20in%20the%20Cage/Query.png)

**The Breakthrough:** The results pointed to **Igor Dekhtyarchuk**. Reports from the Department of Justice (DoJ) identified him as the administrator of **"Marketplace A"**, a sophisticated underground carding shop.

![Igor Dekhtyarchuk](https://raw.githubusercontent.com/AbdelruhmanAskar/0xaskar.github.io/refs/heads/master/assets/images/Opeartion%20Ghost%20in%20the%20Cage/Guy.png)

> **Investigator's Note:** Deep inside the indictment text was the golden lead: _"FBI investigators were able to track Dekhtyarchuk’s presence in the hacking community back to November 2013 when he joined hacker forums under the alias **'floraby'**."_

**Target Alias Identified:** `floraby`.

* * *

### 🕵️ Phase 2: Digital Footprint Analysis (OSINT)

With the alias `floraby`, it was time to map his digital footprint. I used **Sherlock** to scan for the username across social and technical platforms.

**Command:** `sherlock floraby`

![Sherlock Command](https://raw.githubusercontent.com/AbdelruhmanAskar/0xaskar.github.io/refs/heads/master/assets/images/Opeartion%20Ghost%20in%20the%20Cage/All-Accounts.png)

**The Results:** The scan yielded several hits, but the most relevant for a developer/criminal profile were:

*   **GitHub:** `https://www.github.com/floraby`
    
*   **Telegram:** `https://t.me/floraby`
    
*   **Archive.org:** `https://archive.org/details/@floraby`

![Archive](https://raw.githubusercontent.com/AbdelruhmanAskar/0xaskar.github.io/refs/heads/master/assets/images/Opeartion%20Ghost%20in%20the%20Cage/Archive.png)
    

**Analyzing the GitHub Profile:** Navigating to his GitHub confirmed our target. The bio read:

> _"Student at Ural State | Python & Java Enthusiast | Interested in Web Auth."_ _Location: Kamensk-Uralsky, Russia_

This location and education history perfectly matched the FBI’s wanted poster for Dekhtyarchuk.

![Github Profile](https://raw.githubusercontent.com/AbdelruhmanAskar/0xaskar.github.io/refs/heads/master/assets/images/Opeartion%20Ghost%20in%20the%20Cage/Github-Profile.png)

* * *

### 💻 Phase 3: Source Code Audit

Criminals often reuse code or leave "backdoors" for themselves. I audited his repositories and found **`Auth-Project-v1.0`**.

Inside `auth_provider.py`, I discovered a suspicious hardcoded variable:

Python

    # Fallback gateway for encrypted communications
    # Use hex decoder to reveal the secure endpoint
    INTERNAL_GATEWAY = "68747470733a2f2f742e6d652f666c6f726162795f63616765" 

![Python Code](https://raw.githubusercontent.com/AbdelruhmanAskar/0xaskar.github.io/refs/heads/master/assets/images/Opeartion%20Ghost%20in%20the%20Cage/Python-Code.png)

**Decoding the Payload:** I took the hex string to **CyberChef**. Using the **"From Hex"** operation, it revealed a hidden Telegram link: `https://t.me/floraby_cage`

![CyberChef](https://raw.githubusercontent.com/AbdelruhmanAskar/0xaskar.github.io/refs/heads/master/assets/images/Opeartion%20Ghost%20in%20the%20Cage/CyberChef.png)

* * *

### 📱 Phase 4: Infiltration & The Seizure

The link led to a private Telegram channel named **floraby\_cage**. The channel was used to post marketplace inventory (Cookies, SSNs, and bank logs).

![Telegram Channel](https://raw.githubusercontent.com/AbdelruhmanAskar/0xaskar.github.io/refs/heads/master/assets/images/Opeartion%20Ghost%20in%20the%20Cage/Channel.png)

However, the author of the challenge, **0xaskar**, had already compromised the channel, leaving a "Seizure Notice" post:

> **🚫 SEIZED BY 0xaskar** _"To the 'Ghost' running this channel: Your OpSec was good, but your history was better. I left a little souvenir in your backup file."_

![0xaskar Message](https://raw.githubusercontent.com/AbdelruhmanAskar/0xaskar.github.io/refs/heads/master/assets/images/Opeartion%20Ghost%20in%20the%20Cage/Seized-by-0xaskar.png)

**The Backup File:** The post contained a file: `Marketplace_A_Full_Backup.zip`. Upon trying to open it, I was prompted for a password.

![Unzip Folder](https://raw.githubusercontent.com/AbdelruhmanAskar/0xaskar.github.io/refs/heads/master/assets/images/Opeartion%20Ghost%20in%20the%20Cage/Extract-Files.png)

**The Password Hint:**

> _🔒 Archive Password: The name of the place where I learned to code. (My Alma Mater in Kamensk). Format: NameState (Case Sensitive)_

Referring back to the GitHub Bio from Phase 2, the university was **Ural State**.

**Password:** `UralState`

* * *

### 🖼️ Phase 5: Forensics & Extraction

Inside the archive, I found two files:

1.  `READ_BEFORE_PANIC.txt`
    
2.  `0xaskar_was_here_you_are_late.jpg` (A photo of the suspect).

![Suspect Photo](https://raw.githubusercontent.com/AbdelruhmanAskar/0xaskar.github.io/refs/heads/master/assets/images/Opeartion%20Ghost%20in%20the%20Cage/0xaskar_was_here_you_are_late.jpg)
    

**The Final Clue:** The text file contained a taunt:

> _"Finding the cage doesn't mean you own the ghost. The question is: are you just looking at the 'Image', or are you smart enough to see the 'Data'?"_

This directed me toward **Metadata analysis**. I used `exiftool` to inspect the image's hidden headers.

**Command:** `exiftool 0xaskar_was_here_you_are_late.jpg`

![Exiftool Result](https://raw.githubusercontent.com/AbdelruhmanAskar/0xaskar.github.io/refs/heads/master/assets/images/Opeartion%20Ghost%20in%20the%20Cage/Exiftool.png)

**The Result:** Inside the metadata tags, the flag was hidden within the **Artist** field:

*   **Artist:** `N!ghtM4re{0xaskar_hunted_the_floraby_shadow}`
    
*   **Comment:** `0xaskar was here, floraby was there, and you... you are just reading the metadata <3`
    

* * *

### 🚩 Final Flag

**`N!ghtM4re{0xaskar_hunted_the_floraby_shadow}`**
