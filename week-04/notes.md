# Week 4 Notes — Permissions, Searching, and Virtual Machines

**Student Name:** Selerya Ward

**Date Completed:** 10/20/26

Summarize this week's key concepts in your own words — not copy-pasted definitions.

## Key Concepts This Week

- File permissions: read/write/execute × owner/group/other, and reading `ls -l`
- Changing permissions with `chmod` (symbolic and numeric) — and THE GATEKEEPER'S RULE
- Windows ACLs, read with `Get-Acl` (the real-world `icacls` tool does the same job, but is not available in the simulator)
- Wildcards (`*`, `?`, `[ ]`) and searching inside files with `grep`/`Select-String`
- Virtual machines: host vs. guest, the hypervisor, Type 1 vs. Type 2, isolation
- The VM lifecycle: create, start, stop (deallocate), snapshot, delete — and what each costs
- Golden snapshots — how your Weeks 6–12 lab machines are made

## In My Own Words

**Decode `-rw-r-----` audience by audience: who can do what to this file?**

```
The owner has both read and write access to this file, and the group members can read this file. No other users have access to this file.
```

**What is a hypervisor, and what are its two jobs?**

```
The 2 jobs of a hypervisor are to control the hardware running the virtual machines and to manage the operating systems that are running on the allocated hardware. This can be done as a type 1, or bare-metal machine, that controls hardware and manages guest operating systems. An alternative is a type 2, also known as a host, where the hypervisor runs on an OS like traditional computer programs do.
```

**A stopped VM still costs a little money. What is it paying for, and what's the only way to reach a true zero?**

```
A stopped VM still costs to use the storage space it's running on. The only way to reach a true zero would be to make sure the machine is no longer needed and to de-allocate it.
```

---

## Submission Checklist

- [x] I summarized each concept in my own words, not copied definitions

- [x] I answered all three "In My Own Words" prompts

- [x] This file is committed to my portfolio repo at `week-04/notes.md`
