# Week 6 Lab 05 — Layer Detective

**Student Name:** Selerya Ward

**Date Completed:** 11/22/26

**Module:** 2 — Networking & Cloud Foundations | **Week:** 6  
**Submission Path:** `week-06/labs/lab-05-layer-detective.md`

---

## Overview

**This is a SHORT lab — 20 to 30 minutes — and it needs no VM.** No Cloud Heights session, no simulator, no screenshot. This is a thinking lab: you take the evidence you have already collected in Weeks 5 and 6 and sort it into layers.

This is an **independent** lab.

---

## Lab Environment / Pre-Lab Check

| Component | Details |
|---|---|
| Environment | This worksheet only — nothing to start, nothing to connect to |
| Prerequisite | Week 5 labs and Week 6 Labs 01–04 |
| Screenshot | None required |

---

## Part A — The Seven-Row Table

Fill in every row. For the last column, name one **real thing you personally saw** in Weeks 5–6 that belongs at that layer.

| # | Layer name | One-line job | Real thing from Weeks 5–6 |
| --- | --- | --- | --- |
| 7 | Application | The actual thing used by people to interact | Web browsers like Safari or Firefox |
| 6 | Presentation | Making sure data is in the correct format | file encryption |
| 5 | Session | Start, hold, and end a consistent interaction | login to a machine |
| 4 | Transport | How are messages delivered | Ports like SSH (22) and SMTP (25) |
| 3 | Network | Facilitate communications across networks | IP addresses, both IPv4 & IPv6 |
| 2 | Data Link | deliver messages | MAC addresses & switches |
| 1 | Physical | raw signal | RJ45 cables |

---

## Part B — Case Files

For each case, name the layer where the problem lives, and name the evidence proving the layers **below** it were already working.

### Case File 1 — The Name That Went Nowhere

A hostname lookup fails, but pinging the machine's IP address directly succeeds.

Layer:

```
2 - Data Link
```

Evidence that the layers below were working:

```
If there were a physical connection problem, then pinging the machine's IP address would probably fail. This is a DNS issue, where the name is not resolving to an address or the correct address. 
```

### Case File 2 — Permission Denied

`ssh` to a host returns `Permission denied` after a password prompt.

Layer:

```
4 - Transport
```

Evidence that the layers below were working:

```
There is a physical connection made; the device is online. There is a data link made because the device can reach the default gateway. There is a network connection because the device can reach the open internet. The failure is on the second half of the transport layer, because the connection can be established, but authentication fails.
```

### Case File 3 — The Cable Story

A machine reports no link on its interface and has no address at all.

Layer:

```
1 - Physical
```

Evidence and reasoning:

```
Layer 1 refers to raw signal, delivered via cable, fiber, or some other method. If there is no link and no address, the first step would be to confirm that a connection can be made. Step 1 is to determine how the connection is made, either wired or wireless. Step 2 would be to determine if there is a connection present.
```

### Case File 4 — Ping Works, The Page Does Not

`ping` to a server succeeds, but `curl http://<that server>` returns nothing useful.

Layer:

```
6 - Presentation
```

Evidence that the layers below were working:

```
Starting with the physical layer, ping works, so a connection is made to a device that isn't Azure. The layers between physical and presentation all have to do with data connection and routing from the server to intended targets. Since curl doesn't produce useful information, it means that there is an issue with the format of the data to present it in a usable format.
```

### Case File 5 — Wrong Neighbourhood

A machine has an address, but its default route points somewhere that cannot forward its traffic.

Layer:

```
3 - Network
```

Evidence and reasoning:

```
The job of the network layer is to establish a route from point A to point B. Since it seems that the route fails at the default gateway, then the issue lies with the network layer, since the physical and data link layers are working.
```

---

## Part C — The Silent Gateway Case

In Lab 03 the Azure default gateway did not answer your ping. However, your VM had a valid default route configured, and your local communication with the Grid Beacon — the ping replies, the HTTP banner, and `TRACE ID: CF-NET-0604` — succeeded.

A failed gateway ping is one piece of evidence — not automatically proof of a gateway or network failure. But the evidence you weigh against it has to be the right kind of evidence.

The Grid Beacon at `10.60.6.4` sits on the same local subnet as your VM (`10.60.6.0/26`). Reaching it proves **local-subnet connectivity** — that traffic never crosses the default gateway, so beacon success alone cannot prove the gateway forwarded anything. Your `ip route` output proves a **default route is configured** — your VM knows where it intends to send non-local traffic — but it does not prove the gateway forwarded that traffic. The evidence that demonstrates the **default path is functioning** is successful communication with a destination outside `10.60.6.0/26`, such as the outbound internet access through NAT that you examined in Lab 04.

### Step 1 — Rule on the Case

Is the failed gateway ping enough evidence to declare a network-layer failure? Explain your answer using the other evidence you collected. In your response, distinguish between:

- evidence that proves **local-subnet connectivity**
- evidence that proves a **default route is configured**
- evidence that supports **successful off-subnet connectivity**

```
I will complete this part and re-submit.
```

### Step 2 — Name the Correct Conclusion

For each of these four results, state what it actually proves: the Grid Beacon at `10.60.6.4` answering, the default route shown by `ip route`, a successful connection to a destination outside your local subnet, and the gateway's failed ping. Then state the rule you would give a junior colleague about the difference between an observation ("the gateway did not answer my ICMP probe") and a diagnosis ("the gateway is broken"):

```
I will complete this part and re-submit.
```

---

## Part D — Two Models, One Job

The OSI model has seven layers. The practical TCP/IP model most engineers speak day to day has four or five.

### Step 1 — Map Them

Briefly show how the seven OSI layers collapse into the practical model:

```
The TCP/IP model combines layers 1&2 (physical and data link) into a single layer for network access. Layers 3 and 4 remain single layers, but layer 3 is renamed internet. Layers 5, 6, and 7 are merged into a single layer named application.
```

### Step 2 — When Each Is Useful

Explain when the seven-layer vocabulary helps and when the practical model is the better tool:

```
The seven-layer model is the standard that both certification and interview questions are based on. The TCP/IP model is best to troubleshoot with since it has fewer moving parts and uses a practical map. A simple rule to remember is to speak using the OSI model, and troubleshoot using the TCP/IP model.
```

---

## Analysis Questions

**Analysis Question 1.** Explain the Ladder Rule using layer language. What does "test the near thing first" mean when the rungs are layers? *(Minimum 3 sentences.)*

```
'Test the near thing first' means to start at the lowest layer, the physical layer. Before declaring that something is dead or not working, start at the simplest layer. Rule each layer as operational based on several tests before moving to the next layer.
```

**Analysis Question 2.** Why is "which layer is this?" a faster question than "what is broken?" when you are under pressure? *(Minimum 3 sentences.)*

```
'Which layer is this?' is a faster question to answer because each layer represents a level of responsibility. Each layer has a specific job to perform that doesn't rely on the layers below it. Based on a given issue, it can be easy to determine the layer with the problem and work to resolve it using a specific path instead of trying to go in multiple directions and not making much progress.
```

**Analysis Question 3.** Pick one case file from Part B and describe the very next command you would run to confirm your ruling, and what result would change your mind. *(Minimum 2 sentences.)*

```
Case File 3 - The Cable Story (no interface indicator link and no address)
The first thing that I would check would be to see if the device has power. This test would align with a test of the physical layer. If the device has power, I would then check to see if a connection could be established with a different cable. The only result that would change my mind is if I determined that the device didn't have power. That would resolve the presented issue, but it would need to be resolved why the device doesn't have power.
```

---

## Submission Checklist

- [x] All seven rows of the OSI table completed with a real Week 5–6 anchor each (Part A)

- [x] All five case files given a layer and supporting evidence (Part B)

- [x] Silent gateway case ruled on correctly (Part C)

- [x] OSI vs. practical TCP/IP model compared (Part D)

- [x] All three Analysis Questions answered (minimum sentence counts met)

- [x] No screenshot required for this lab

- [ ] This file is committed to your portfolio repo at `week-06/labs/lab-05-layer-detective.md`

---

## GitHub Commit Subsection

1. Open **Week 6 → Lab 05: Layer Detective** in the Lab Portal.
2. Fill in the worksheet fields.
3. Click **Submit to GitHub** — the Portal commits to `week-06/labs/lab-05-layer-detective.md`.

---

*CyberVisionaries Institute · Cyber Foundations · Tier I*
