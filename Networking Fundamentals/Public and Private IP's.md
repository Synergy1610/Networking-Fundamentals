---
aliases:
  - Public IP
  - Private IP
---
#networking 

### Public & Private IP Addresses

**The problem:** IPv4 only has ~4.3 billion addresses (32-bit) — nowhere near enough for every device in the world to have a globally unique one. So IPs are split into two categories.

#### Public IP
- Globally unique — no two devices on the internet share one at the same time
- Assigned by ISPs (allocated from regional registries)
- This is the address that identifies _you_ to the outside internet — specifically, your **router's** outward-facing interface

#### Private IP
- Not globally unique — freely reused across different private networks, since they're never routed on the public internet
- Reserved ranges:
    - `10.0.0.0 – 10.255.255.255`
    - `172.16.0.0 – 172.31.255.255`
    - `192.168.0.0 – 192.168.255.255`
- Devices on your home network (phone, laptop) use these — e.g. `192.168.1.10`

#### How they connect: NAT
Your router has **both** — a private IP facing your home network (its gateway) and a public IP facing the internet. When a device sends traffic out, the router performs **NAT (Network Address Translation)**: it swaps the private source IP for its own public IP before forwarding it out.

This is why every device in your house shows the _same_ public IP on an "IP lookup" — from the internet's view, all traffic looks like it's coming from one device (the router).

**Note:** Specifically, home routers use **PAT (Port Address Translation)** — they also swap the _source port_, and keep a NAT table mapping `public port → private IP + private port`. This is how the router knows which internal device a response belongs to when it comes back, and how multiple devices can share one public IP without conflicts.

#### Example NAT Table
Say the laptop and phone both happen to pick source port `50001` internally — the router assigns each a _different_ public port to avoid collisions:

|Public IP:Port|Private IP:Port|Device|
|---|---|---|
|203.0.113.5 : 62000|192.168.1.10 : 50001|Laptop|
|203.0.113.5 : 62001|192.168.1.15 : 50001|Phone|

When a response arrives at `203.0.113.5 : 62000`, the router looks up the table, sees it maps to `192.168.1.10 : 50001`, rewrites the packet, and forwards it to the laptop — normal MAC/switch delivery from there.

