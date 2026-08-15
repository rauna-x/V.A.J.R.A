# 🛡️ PROJECT VAJRA (V.A.J.R.A.)
> **Vulnerability Assessment & Joint Remediation Autonomous Core**  
> *Sovereign Air-Gapped Multi-Host Cyber Defense & Self-Healing Engine*


# Working
<img width="400" height="227" alt="Image" src="https://github.com/user-attachments/assets/a6f4af88-3657-4846-9375-67eb6d4e4208" />

# Details & Description 
[PROJECT VAJRA - Cyber Defense Deck.pdf](https://github.com/user-attachments/files/31094989/PROJECT.VAJRA.-.Cyber.Defense.Deck.pdf)
---

## 📌 Overview
**PROJECT VAJRA** is an indigenous, defense-grade autonomous cybersecurity platform engineered in **Golang**. Built for isolated war rooms, Command & Control (C4I) networks, and Critical National Infrastructure (CNI), VAJRA delivers real-time vulnerability discovery, offline threat reasoning (MITRE ATT&CK mapping), and autonomous 1-click self-hardening scripts without routing a single byte of telemetry to external cloud servers.

---

## ⚡ Core Technical Pillars

* 🚀 **Zero-Cloud & 100% Air-Gapped:** Zero external API calls. Runs locally on sovereign hardware with local Llama-3 models via Ollama.
* ⚡ **High-Speed Concurrency (Goroutines):** Audits entire subnets, IP lists, or multi-host fleets in parallel using a lightweight Go Worker Pool.
* 🧠 **Offline RAG Threat Intelligence:** Integrated sovereign dictionary mapping open services directly to CVEs, CVSS v3.1 severities, and MITRE ATT&CK tactics (e.g., T1190, T1021).
* 🛡️ **Autonomous Self-Healing:** Generates pre-validated, executable Bash scripts (`*_harden.sh`) to instantly patch firewall configurations and disable vulnerable services.
* 📦 **Single Static Binary:** Compiles into a single portable binary (~15MB) runnable directly from secure media (USB) on Linux / BharatOS / BOSS Linux.

---

## 🏗️ Architecture Pipeline

```text
[Target / Subnet Ingestion]
           │
           ▼
[Stealth Recon Engine] ──────► Nmap (Fast Port Mapping) + Ffuf + Nuclei
           │
           ▼
[Sovereign RAG Processor] ───► Offline Knowledge Injection (CVEs + MITRE IDs)
           │
           ▼
[Local Edge-AI Core] ────────► Local Llama-3 Inference (via Ollama)
           │
     ┌─────┴────────────────────────────────────────┐
     ▼                                              ▼
[outputs/<target>_VAJRA_Report.md]     [outputs/<target>_harden.sh]
(Executive & Tactical Audit)           (1-Click Auto-Remediation Script)

## 🛠️ Installation & Setup
Prerequisites
Linux / Unix (Ubuntu, Debian, BOSS Linux, Kali, Fedora)

Go (Golang) >= 1.22

Nmap, Ffuf, and Nuclei installed on system PATH

Ollama running locally with llama3

## Ouick Start

# 1. Clone Repository
git clone [https://github.com/](https://github.com/)<your-username>/VAJRA.git
cd VAJRA

# 2. Start Local AI Engine
ollama run llama3

# 3. Compile Standalone Go Binary
go build -o vajra main.go

# 4. Verify Execution
./vajra -h


## 1. Single Target Audit
Bash
./vajra -t 192.168.1.10

2. Multi-Host Concurrency Audit
Bash
./vajra -t 192.168.1.10,192.168.1.20,scanme.nmap.org -c 3

3. Fleet-Wide Subnet File Audit
Bash
./vajra -f target.txt -c 5

4. Custom Wordlist Web Surface Discovery
Bash
./vajra -t 10.0.0.1 -w wordlist.txt

📊 Output Artifacts
All scan results and auto-generated countermeasures are organized in outputs/:

outputs/FLEET_DEFENSE_SUMMARY.md — Consolidated executive security posture for all scanned hosts.

outputs/<target>_VAJRA_Report.md — Detailed tactical security audit with CVSS 3.1 scoring & MITRE vectors.

outputs/<target>_harden.sh — Executable bash script for immediate defense deployment.

👤 Author
Raunak Chaturvedi


