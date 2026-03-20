<p align="center">


<h2>Video Demonstration</h2>

- ### [YouTube: Day 20 Lab STP](https://www.youtube.com/watch?v=I_b3BP5QQ-I)

<h2>Environments and Technologies Used</h2>

- Jeremy's IT Lab Youtube Channel
- Cisco Packet Tracer
  

  
<h2>Operating Systems Used </h2>

- Cisco IOS


<h2>Step-by-Step</h2>

<b>🔑 Core Concepts from This Lab</b>

1. Root Bridge Election

Every STP topology has one root bridge

It’s chosen based on the lowest Bridge ID, which consists of:

Priority (lower = better)

MAC address (tie-breaker)

👉 In this lab:

SW3 becomes the root bridge (lowest priority)

2. Port Roles (VERY IMPORTANT for CCNA)

There are 3 main port roles:

🟢 Root Port (RP)

The best path to the root bridge

One per switch (non-root switches only)

🔵 Designated Port (DP)

The best port on a segment

Always forwarding

All ports on the root bridge are designated

🔴 Non-Designated Port (Blocked / Alternate)

Prevents loops

Does NOT forward traffic

3. How Root Ports Are Chosen

Order of decision:

Lowest root path cost

If tie → Lowest neighbor bridge ID

If still tie → Lowest neighbor port ID

👉 Example from lab:

SW2 picks G0/1 as root port because cost = 8 (better than 19)

4. Designated vs Non-Designated Ports

On each link:

One side = Designated (forwarding)

Other side = Blocked (non-designated)

Rule:

Switch with lower root cost wins → becomes designated

5. Key CLI Commands You Need to Know

Check STP status:

show spanning-tree

Filter by VLAN:

show spanning-tree vlan 1

More detailed info:

show spanning-tree detail

Summary view:

show spanning-tree summary

6. Important STP Timers (Memorize These)

Default values:

Hello Time: 2 seconds

Max Age: 20 seconds

Forward Delay: 15 seconds

👉 These control how STP converges and prevents loops.

7. Key Observations from the Lab

Root bridge (SW3) → all ports are Designated + Forwarding

Non-root switches:

Have 1 root port

Some ports are blocked to prevent loops

No blocked ports exist on the root bridge

8. Why STP Exists (Big Picture)

Without STP:

Redundant links = broadcast storms

MAC table instability

Network meltdown 😬

STP:

Prevents loops

Keeps redundancy

Blocks unnecessary paths

🧠 Quick Memory Trick

Root = All Designated

Each switch = 1 Root Port

One link side blocks
