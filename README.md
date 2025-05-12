# HollowRoot – Full-Stack Enterprise Security Lab

HollowRoot is a full-stack cybersecurity simulation project designed to showcase realistic insider threat paths across both **Active Directory (AD)** and **Azure cloud infrastructure**.

This lab environment is built to feel like something you’d actually see in a fast-growing fintech company — messy permissions, rushed cloud rollout, reused credentials, and too much trust in too many places.

---

## 🧠 Project Goal

The goal of HollowRoot is to **simulate how a rogue insider can move from intern-level access to full domain and cloud compromise**, using real-world misconfigurations and security oversights.

It’s designed to cover both **red team escalation paths** and **blue team detection failures**, making it ideal for learning, documentation, or resume-worthy demos.

---

## 🗂️ What This Project Covers

- Structured Active Directory environment (`blackridge.local`) with users, departments, RBAC, and NTFS-secured shared folders
- Realistic group structures using role-based access control (RBAC)
- Automated PowerShell scripts for user + group deployment
- Windows 10 client setup for internal access simulation
- RDP + file share scenarios
- Azure tenant setup mimicking a hybrid org:
  - Bad identity hygiene
  - Key Vault exposure
  - Public blob storage leaks
  - Credential hardcoding
- Credential leak on-prem (`.ps1`) used to pivot into Azure
- Red team escalation design baked into the misconfigs

---

## 📖 Story: “The Intern Who Got Tired of Waiting”

_Eliot Drake_ was a quiet, hard-working IT intern at Blackridge Bank.

He clocked in early, stayed late, and did everything he was told. For a while, he thought it might pay off — maybe even land him a full-time spot. But one afternoon, he overheard his manager during a Teams call:

> “We’ll probably just cut him loose. He hasn’t shown any real initiative.”

Something snapped.

Over the next few weeks, Eliot stopped trying to impress and started exploring. He noticed that executives had domain admin rights. That PowerShell scripts had saved credentials in plain text. That cloud access was wide open — and no one was watching.

He didn’t have to break in.  
He was already inside.

---

## 🔍 Why This Project Exists

I built this to learn what companies actually do wrong, not just what textbooks say.

HollowRoot is meant to feel real — full of corner-cutting, shadow admins, forgotten shares, and policies that "someone meant to fix." The kind of environment where compromise doesn't happen because of zero-days, but because no one ever cleaned up after themselves.

---


## 🛠️ Tools Used

- Windows Server 2022
- Windows 10 (client)
- Proxmox (for virtualization)
- Azure Portal (free tier)
- PowerShell
- Microsoft Entra ID (formerly Azure AD)

---

## 📬 Contact / Follow-Up

This project is a work-in-progress designed for learning and portfolio building.  
If you're curious or want to build something similar, feel free to reach out or follow along.

