# How I Met the Attacker – Part 2

## Overview

This is another real incident that changed the way I look at network security.

One of my friends asked me to visit a shop and solve some network-related issues. They had multiple PCs in the main branch and a few systems in a remote branch.

An intern was hired earlier to set up the network.

The setup was simple:

- Main branch had a Windows machine acting as a server
- Remote branch users were connecting using RDP
- They had a static public IP
- Port 3389 was forwarded from the router directly to the server

Everything worked fine initially.

One day they noticed customer data inside OneDrive was getting deleted.

Luckily, they had backups and restored the data.

A few days later, same issue again.

That’s when they asked me to check the setup properly.

After going through the router configuration and systems, I found the issue.

Port 3389 (RDP) was directly exposed to the internet through port forwarding.

Attackers somehow gained access to the machine, most likely through brute-force attempts. There was no antivirus protection in the environment either.

Eventually:

- Data was deleted
- Systems were locked
- A Bitcoin ransomware message appeared
- Entire PC was BitLocker locked

At that point it was clear — the problem was not the users, it was the exposure.

---

## What Went Wrong

- RDP exposed directly to the internet
- Port forwarding enabled for 3389
- Static public IP accessible publicly
- No VPN for remote access
- No antivirus protection
- Weak security controls

---

## Improved Architecture

After identifying the issue, the architecture was redesigned in a more secure way.

- Removed public RDP exposure
- Disabled port forwarding for 3389
- Configured OpenVPN server on the HQ router
- Remote branch connected securely using OpenVPN client
- Installed antivirus protection
- Restricted direct public access

![Improved Architecture](../assets/part2-openvpn-architecture.png)

---

## Lesson Learned

Just because remote access works doesn’t mean it should be exposed publicly.

A lot of attacks happen because of simple misconfigurations.

Sometimes security improvements are not about expensive tools — just better decisions.

---

Repository:
https://github.com/onielgmail/Cyber-dumps