---
layout: single
title: "OSINT Write-up: A Weird Combo"
excerpt: "My first time as an OSINT author at N!ghtM4re CTF! Let's solve this 'Weird Combo' together."
date: 2026-02-10
categories: [OSINT]
author_profile: true
---

# 🕵️‍♂️ OSINT Challenge: A Weird Combo

Hello everyone! I am super excited to share that I was an **Author** for the first time in the **N!ghtM4re CTF**! 🥳 

I created an OSINT challenge called **"A Weird Combo"**. It was a fun experience blending real-world locations with a bit of a riddle. Let's see how to solve it step-by-step!

---

## 📝 The Challenge Description

> "I took this photo right before hopping on the metro. I was starving, so I only rode for one station and got off. The station I arrived at made me feel like I was protected from the rain, even though the sun was shining!
> 
> Just a few steps away from the exit, I found a restaurant with a very weird menu. Who would have thought you could order Liver and Brains along with a Crepe from the same place?! The name is a bit of a mouthful, but the spot is iconic.
> 
> I saved their phone number from the Google Maps. Can you find it?"

**Flag Format:** `N!ghtM4re{Restaurant Phone Number}`

---

## 🔍 Step 1: Where did we start?

First, I had a photo of a metro station. I used **Google Reverse Image Search** and added the keyword "Metro" to help the search engine.

![Reverse Search Result](/assets/images/reverse-image.png)

The search confirmed that the starting point is **Kolleyet El-Zeraa Station** (Faculty of Agriculture). 

---

## 🚇 Step 2: One station away... but where?

The description says: *"I only rode for one station and got off."*

I checked the official [Cairo Metro website](https://www.cairometro.gov.eg/ar/stations/20?information=1) to see the map. From Kolleyet El-Zeraa, riding for one station leads to only two possibilities:
1. **Shobra El-Kheima Station**
2. **Mazallat Station**

![Metro Map](/assets/images/paths.png)

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

![Google Maps Search](/assets/images/google-map.png)

I found it: **"Kebda w Mokh w Crepe El-Iman Asran" (كبدة ومخ وكريب الايمان عصران)**. The name is definitely a "mouthful"!

I checked the **"About"** section on Google Maps to find the phone number.

![Restaurant Phone Number](/assets/images/resturant.png)

---

## 🏁 The Flag

The phone number listed is `01111132001`.

**Final Flag:** `N!ghtM4re{01111132001}`

---

## 🎓 Skills Learned

* **Image Recognition:** Using Reverse Image Search to identify landmarks.
* **Logic & Deduction:** Using a map and description hints to narrow down locations.
* **Arabic Language Hints:** Understanding how "Mazallat" relates to "Rain protection."
* **Google Maps OSINT:** Extracting specific data (phone numbers) from business listings.

Thanks for playing my challenge! Stay tuned for more! 🚀
