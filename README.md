## Series: How I Met the Attacker

This repository is a collection of my learning in cybersecurity based on real situations.

In this series, I share mistakes I made, what went wrong, and what I learned from it. The idea is to keep things simple and practical.

---

### Part 1: Public Exposure and Database Compromise

In my early setup, I was focused only on making things work.

- EC2 was in a public subnet  
- MongoDB was open to the internet  
- Ports were exposed for easy access  

Everything was working fine until one day the database was gone.

Instead, there was a message asking for payment.

That’s when I understood the mistake. I had exposed everything to the internet.

What I learned from this:

- Do not expose database to the internet  
- Use private subnet for backend and database  
- Restrict access properly  
- Working setup does not mean secure setup  

This incident made me redesign the architecture in a more secure way.

---

### Purpose

This is not theory.

It is based on real mistakes and real learning.
