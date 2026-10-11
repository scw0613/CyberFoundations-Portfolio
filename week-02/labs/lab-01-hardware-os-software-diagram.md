# Week 2 Lab — Cybersecurity Landscape & Digital Infrastructure Overview

**Student Name:** Selerya Ward

**Date Completed:** 10/10/26

**Module:** 1 — Digital Infrastructure & CLI | **Week:** 2  
**Submission Path:** `week-02/labs/lab-01-hardware-os-software-diagram.md`

---

## Overview

In this lab, you build a working mental model of the system you'll be securing throughout this course: the hardware, operating system, and software layers that make up every computer, and where the cybersecurity field fits around them. This lab has two parts. Part A connects this week's material to the CyberFoundations City map. Part B has you build and explain a diagram of how a computer's hardware, OS, and software layers interact.

**No terminal or command line is required this week** — that starts in Week 3.

---

## Lab Environment

| Component | Details |
|---|---|
| Environment | Browser-based Lab Portal (Module 1 orientation) |
| Required Materials | CyberFoundations City map; a diagram tool of your choice (hand-drawn and photographed, or any digital tool) |

**Prerequisite:** Portfolio repo created from the CyberFoundations student template in Week 1. This file is already in your repo at `week-02/labs/lab-01-hardware-os-software-diagram.md`, ready to fill in.

**New to the Lab Portal?** Watch this short walkthrough of how to find your Week 2 lab worksheet: [Accessing the Lab Worksheet — Step by Step](PASTE-VIDEO-LINK-HERE) *(~3 min)*.

---

## Part A — CyberFoundations City & the Cybersecurity Landscape

The CyberFoundations City map is your visual guide to the next 11 weeks. Each district represents a module of this course. This part connects this week's material to the map you were introduced to in Week 1.

### Step 1 — Open the Lab Portal Orientation Module

Log into the Lab Portal with your Microsoft account. From your Student Dashboard, open the **Module 1 orientation** module.

### Step 2 — Complete the Orientation Walkthrough

Work through the orientation content. It covers the same hardware/OS/software material as this week's lessons from a different angle — use it to check your understanding, not to replace the lessons.

### Step 3 — Locate This Week's District on the City Map

Open the CyberFoundations City map (introduced in Week 1, Lesson 6). Identify which district corresponds to Module 1 — Digital Infrastructure & CLI.

**District name:** Foundry District

```
(enter the district name)
```

**Why this district fits this week's topics (1–2 sentences):**

```
The Foundry District represents the foundation of this course. On the surface, it may not seem busy, but if someone takes a closer look, there is lots that can be observed and learned. Diving even deeper reveals how smaller pieces fit together into larger and larger pieces, as well as how each piece has a specific purpose to keep everything running smoothly. On the opposite side, it's possible to imagine how the failure of a small component can easily balloon into a larger event.
```

---

## Part B — Hardware, OS, and Software Diagram

A computer is a stack of layers: physical hardware at the bottom, an operating system managing that hardware in the middle, and the software you actually use on top. This part has you draw that stack and explain it in your own words.

### Step 1 — Identify the Layers

Before drawing anything, list the three layers you'll diagram and one example of what lives at each layer.

**Hardware layer — one example component:** RAM - Random Access Memory

```
(e.g., CPU, RAM, storage — your choice)
```

**Operating system layer — name an OS:** Windows 11

```
(e.g., Windows, Linux, macOS)
```

**Software layer — one example application:** Firefox

```
(e.g., a web browser, a word processor)
```

### Step 2 — Sketch Your Diagram

Sketch a simple diagram (hand-drawn and photographed, or built in any digital tool) showing how the hardware, OS, and software layers stack and interact. Arrows or labels showing "what talks to what" matter more than visual polish. If you'd like a free browser-based option instead of hand-drawing, try [draw.io](https://www.drawio.com/) — no account required to get started.

### Step 3 — Upload and Embed Your Diagram

Upload your diagram image directly into your repo's assets folder — keep it there rather than pasting it loose into this file, so all of this week's images stay together and organized.

1. Go to your portfolio repository on GitHub.com and navigate to `assets/screenshots/week-02/`.
2. Click **Add file → Upload files**, then drag in your diagram image, and give it a descriptive name (lowercase, hyphens, no spaces, no timestamps — e.g. `hardware-os-software-diagram.png`).
3. Scroll down and click **Commit changes**.
4. Click on the uploaded image's filename to open it — you'll see the image itself displayed on the page.
5. Right-click directly on the image and choose **Copy image address** (Chrome/Edge) or **Copy Image Link** (Firefox).
6. Come back to this file, open the pencil (edit) icon, and paste that link into the embed line below, in place of the placeholder:

![Hardware/OS/software diagram](https://raw.githubusercontent.com/scw0613/CyberFoundations-Portfolio/refs/heads/main/assets/screenshots/week-02/hardware-os-software-diagram.png)

**If right-click doesn't show that option:** click the small download-arrow icon in the top-right of the image preview instead, then copy the URL from your browser's address bar.

**My Diagram:**

### Step 4 — Explain Your Diagram

In your own words — not a copied definition — explain how the three layers interact. Reference your own diagram directly.

```
The RAM is hardware that is one of the foundation components of a computer. As the user clicks on icons and navigates through menus to open files and programs, instructions are sent continuously to the RAM to process the instructions. If an icon, like Firefox is clicked, then the OS interprets that instruction to open Firefox. That instruction is sent to the RAM to allocate the needed memory to run the software application and keep it running until it is closed.
```

---

## Analysis Questions

Answer each question in your own words. These questions connect what you did in Parts A and B to the bigger picture of this course.

### Analysis Question 1

If the operating system crashed on the computer you diagrammed, which layer(s) would stop working, and which (if any) would keep working? Explain your reasoning.

```
If the OS crashed, then only the RAM would continue functioning for a short time. Since the OS isn't running, then new programs cannot be opened, and currently open programs can't process new instructions. Ultimately, the computer would need to be restarted, which would then clear the RAM since it is volatile memory, and allow the OS to start again and hopefully function properly.
```

### Analysis Question 2

Pick one piece of software you use daily. Trace it down through the OS to the hardware it ultimately depends on. What would happen to that software if the hardware layer failed?

```
A software program that I use daily is iTunes. It relies on various services maintained by the OS to keep the program running. If the hard drive failed, then iTunes would stop working since it relies on the OS, which relies on the hard drive. This is why a hard drive failure can be catastrophic since the other hardware components rely on the OS running on the hard drive to process instructions. 
```

### Analysis Question 3

Explain, in your own words, why a cybersecurity professional needs to understand all three layers — hardware, OS, and software — rather than just the software layer where most visible attacks (like phishing emails) happen.

```
It's important for a cybersecurity professional to understand hardware, OS, and software so that proper investigation can be done to confirm both proper operation and investigate possible breaches. If someone doesn't understand hardware components, it may be improperly assumed that all is well when an OS service is running when it should not be, or a program is allowing access that it shouldn't. Asking the right questions is the key to understanding what is happening, what is being affected, and how to correct the problem.
```

---

## Lab Report Questions

Answer each question in complete sentences.

**1. What is the cybersecurity landscape, and why does it matter to someone starting this course?**

```
The cybersecurity landscape is complicated, and that especially matters for someone starting this course because there are more connections that can be made, and with more connections, there are more opportunities for vulnerabilities to be discovered and possibly exploited. The landscape is more fuzzy with the advancement of AI; it is now possible for someone to use AI for the wrong reasons and cause damage. On the opposite side, a lot of companies are using AI as a foundation to secure critical infrastructure and other assets. It's important to understand how things work at a base level in order to be properly prepared for an interview, but also understand that there may be software that runs in the background that previously relied on people. The future continues to get more complicated.
```

**2. Which CyberFoundations City district did you identify in Part A, and how does its theme connect to the hardware/OS/software material in Part B?**

```
I identified the Foundry district, and it seems like it functions as the hardware. When looking from farther away, it can be difficult to see how things fit together. Taking a closer look, it is more that just hardware. It's the CPU, the RAM, the hard drive, and so on. Each component has a job and relies on another component to function properly. If any one component fails, then the other components cannot function as they should, if they can function at all. If the CPU fails, then other components can only possibly communicate that they cannot function due to a failure.
```

**3. Of the three layers (hardware, OS, software), which one do you think is hardest to secure, and why?**

```
I think that the OS can be the hardest to secure since there are so many components at work. There are services running in the background to keep hardware functioning, and there are software components functioning at the layer above. The proper permissions have to be granted only to authorized users and programs. As technology advances, then components have to be tested and updated only when has been shown that it is safe to do so. If a vulnerability is discovered, hopefully it can be patched and resolved before it is exploited.
```

---

## Submission Checklist

- [x] Lab Portal Module 1 orientation completed

- [x] District identified and explained

- [x] Hardware, OS, and software layer examples listed

- [x] Diagram uploaded to `assets/screenshots/week-02/` and embedded using a copied image link (not pasted loose, not a local file path)

- [x] Diagram explanation written in your own words (minimum 3 sentences)

- [x] All three Analysis Questions answered (minimum sentence counts met)

- [x] All three Lab Report Questions answered in complete sentences

- [x] This file is committed to your portfolio repo at `week-02/labs/lab-01-hardware-os-software-diagram.md`
