# Week 5 Notes — The Grid: Addresses, Names, Ports, and Diagnostics

**Student Name:** Selerya Ward

**Date Completed:** 10/25/26

Summarize this week's key concepts in your own words — not copy-pasted definitions.

## Key Concepts This Week

- IP addresses — the dotted-quad number every device on a network needs (`10.20.5.42` on The Grid)
- The subnet mask — the answer to "which addresses are my neighbours?" (`/24` = `255.255.255.0`)
- The default gateway — the door out of your neighbourhood (`10.20.5.1` on The Grid)
- Private vs public addresses — `10.x`, `172.16–31.x`, and `192.168.x` are *inside* addresses
- DNS — the Grid's Directory Board: a name goes in, an IP address comes out
- NXDOMAIN vs a host that resolves but doesn't answer — two different failures with two different causes
- DHCP — the Address Office: leases, why addresses change, why a laptop "just works" on a new network
- Ports — the numbered doors on a building: 22 SSH, 53 DNS, 80 HTTP, 443 HTTPS, 3389 RDP, 25 SMTP
- TCP vs UDP — a confirmed conversation vs a shout across the room
- The TCP handshake — SYN → SYN-ACK → ACK (packets 7, 8 and 9 in Lab 03)
- The diagnostic toolkit — `ping` (does it answer this test?), `traceroute` (which hops answer?), `dig` (what number is behind that name?). Evidence limits: no ping reply doesn't prove a host is off, and `* * *` means no reply came back, not proof of the exact fault
- **THE LADDER RULE** — check yourself → check your gateway → check the target by NAME → check the target by IP → trace the path. *Work outward, one rung at a time, and let the evidence pick the culprit.*

## My Command Table

You learned the same five jobs twice this week — once in bash, once in PowerShell. Fill the pairs in from memory if you can, and check them afterwards. Type straight into the box below — one job per line, e.g. `show my address: ip addr | ipconfig`. This table is worth keeping.

The bash command and its PowerShell equivalent for each job — show my own address, show my default gateway, test reachability, trace the path, look up a name:

```
Show my address: ip addr | ipconfig  
Show my gateway: ip route | ipconfig
Is it alive?  ping | Test-Connection 
Where does it stop? traceroute | tracert 
What number is behind that name?  dig | Resolve-DnsName
```

## In My Own Words

Your machine has three numbers: an address, a subnet mask, and a default gateway. Explain what each one is for, the way you'd explain it to someone who has never heard those words.

```
The address, or IP address, is the group of numbers assigned to the computer so that it can communicate with other computers. The subnet mask is the group of numbers that identifies the devices that are on the same network or in the same neighborhood. The default gateway is the way out of the specific neighborhood; it's like a traffic light at a busy intersection.
```

What does DNS actually do? Include the difference between a name that comes back "Name or service not known" (NXDOMAIN) and a name that resolves perfectly well to a host that never answers.

```
DNS translates between the name of the device and the network address of the device. If a device name has a response of 'name or service not known' it means that either the name isn't known, or there is an issue with the service. If a device name responds with an IP address, then DNS has done its job. It has responded with a temporary address to a device that needed one.
```

An IP address gets your traffic to the right building. What does a port number add to that, and why would a defender care how many doors are open?

```
The port number specifies the office or suite number inside the building where traffic should be directed. A defender cares how many doors are open because if a door is open and no longer being used, then it is a vulnerability. A door should only remain open while it is being used; it should be closed once the job is complete. That rule is a foundational one that helps to keep networks secure.
```

Write out THE LADDER RULE — all five rungs, in order — and say why running them in that order matters more than running them fast.

```
1. Check yourself and the gateway - make sure the workstation has a valid address, and where traffic leaves from.
2. Is it possible to leave the neighborhood? Ping the default gateway to rule out the problem.
3. Check the target by NAME 
4. Check the target by IP 
5. Trace the path to the target
```

What is DHCP, and why does your laptop get an address automatically on a network it has never joined before, while a server like `grid-dns` keeps the same address permanently?

```
DHCP stands for Dynamic Host Configuration Protocol, and it means that a DNS server will automatically assign an IP address to a device on the network by loaning out an available address from a pool of available addresses. There are addresses that are kept available for lease; these can change. Likewise, there are device addresses that can be permanent, like the address for grid-dns.
```

---

## Submission Checklist

- [x] I summarized each concept in my own words, not copied definitions

- [x] I completed the bash-to-PowerShell command table

- [x] I answered all five "In My Own Words" prompts

- [x] This file is committed to my portfolio repo at `week-05/notes.md`

---

*CyberVisionaries Institute — Cyber Foundations, Tier I*
