# HollowRoot – Full-Stack Enterprise Security Lab

HollowRoot is a full-stack cybersecurity lab that simulates what happens when a company builds fast, configures badly, and underestimates the risks of insider threats.

It’s built to mimic a realistic fintech company — **Blackridge Bank** — with an internal Active Directory environment, a cloud-connected Azure tenant, and all the messy identity and access problems that real organizations often overlook.

This isn’t just a red team lab. It’s the whole picture:
- **Blue team setup**
- **Red team abuse**
- **Post-breach analysis**
- **Hardening + remediation**

---

## 🧠 Project Goal

To simulate how a trusted insider — starting with basic intern access — can escalate privileges, compromise sensitive systems, and eventually breach the cloud, all because no one locked things down.

And then, to flip the script:  
**How do we defend against it? What could’ve stopped it?**

---

## 🧩 Project Structure

### Phase 1 – Foundation & Infrastructure

- Deployed an **Active Directory environment (`blackridge.local`)**
  - Structured by site and department
  - Users, security groups, and mapped shared drives
- Wrote PowerShell automation to generate:
  - 100 users
  - Department-based OU + group assignments
  - Human-style passwords
- Locked down folders with NTFS + group permissions
- Shared folders via SMB
- Deployed a Windows 10 client to test permissions and simulate user actions

### Phase 2 – Insider Attack (Red Team)

- Introduced **Eliot**, a quiet IT intern with too much access
- Discovered overprivileged execs, reused credentials, and unsecured shares
- Found a `.ps1` script with **hardcoded Azure credentials**
- Pivoted from domain to Azure using built-in tools (no malware)
- Extracted secrets from **Azure Key Vault**
- Downloaded financials from **public blob storage**
- Planted a logic bomb for cleanup

### Phase 3 – Blue Team Response

After the breach, we wrote a **remediation plan** based on real-world blue team practices:
- How GPOs could’ve prevented lateral movement
- How conditional access and MFA would’ve stopped the cloud pivot
- How logging and alerts could’ve revealed Eliot’s activity early
- How to fix overprivileged groups, clean up stale identities, and secure cloud storage properly

---

## 📖 Short Story: “The Intern Who Got Tired of Waiting”

_Eliot Drake_ was the type of intern most teams want — early, eager, and quiet.

But after overhearing his manager talk about letting him go, he decided to stop waiting for a shot and start making moves.

He found credentials in shared folders. Noticed that some execs had domain admin. Saw that cloud access wasn’t being monitored.

He didn’t break in.  
He just kept going.

---

## 🧪 Why This Lab Exists

I didn’t want to just build something “secure.”  
I wanted to build something that looked normal — and was quietly dangerous.

HollowRoot is the kind of place where:
- MFA was “on the roadmap”
- Scripts with passwords were left on the share drive
- Domain Admins didn’t remember who was in what group
- Cloud was rushed and no one went back to fix it

This project is about understanding how attacks happen — and what can be done after.

---

## 🛠️ Stack

- Windows Server 2022 (AD, file shares, group policies)
- Windows 10 (domain-joined client)
- PowerShell (automation + internal abuse)
- Azure (IAM, Storage, Key Vault, Entra ID)
- Proxmox (virtualization for lab)

---

## 🧾 Deliverables

- `Deploy-BlackridgeAD.ps1` – user + group automation
- `Phase_1_Notes.md` – clean walkthrough of AD + Azure setup
- `Phase_2_RedTeam.md` – Eliot’s attack chain
- `Phase_3_BlueTeamRemediation.md` – hardening recommendations
- `Phase_1_Report.pdf` – polished summary for portfolio use

---

## 📬 Contact / Follow-Up

This lab is ongoing — future phases will expand into logging, SIEM alerts, lateral detection, and more.

If you’re building something similar or want to fork and expand on HollowRoot, feel free to reach out or contribute.

Let’s build bad infrastructure, so we can get better at defending it.
