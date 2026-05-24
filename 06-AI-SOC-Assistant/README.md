# 🤖 Project 06 — AI-Powered SOC Assistant with Telegram

**Tools:** Hermes Agent, Ollama, Neo4j, Telegram Bot API, Systemd  
**Environment:** Kali Linux (VirtualBox)  
**Bot Name:** Ghost_ForensicSOC_Bot  
**Date:** May 2026  
**Status:** ✅ Completed

---

## 🎯 Objective

Build a remotely accessible AI-powered SOC assistant capable of performing
real-time cybersecurity analysis and system inspection through Telegram.

---

## 🏗️ Architecture

    Telegram App
         ↓
    Telegram Bot API (Ghost_ForensicSOC_Bot)
         ↓
    Hermes Agent Gateway (Kali Linux)
         ↓
    Ollama LLM (Local AI — no cloud dependency)
         ↓
    Neo4j (Knowledge Graph / OSINT correlation)
         ↓
    System Inspection & Security Analysis

---

## 🛠️ Stack

| Component | Purpose | Address |
|---|---|---|
| **Hermes Agent** | AI orchestration & Telegram gateway | Local service |
| **Ollama** | Local LLM inference — no API limits | 127.0.0.1:11434 |
| **Neo4j** | Knowledge graphs, attack path visualization | 127.0.0.1:7474 |
| **Telegram Bot API** | Remote command interface | @Ghost_ForensicSOC_Bot |
| **Systemd** | Service management & auto-restart | User services |

---

## 🔧 Environment

| Component | Value |
|---|---|
| OS | Kali Linux |
| Virtualization | VirtualBox NAT |
| VM IP | 10.0.2.15 |
| Hostname | TUUUEREEEUNAAABURLAA |

---

## 🧪 Commands Used

Monitor gateway logs:

    journalctl --user -u hermes-gateway -f -l

Restart gateway service:

    systemctl --user restart hermes-gateway

Validate bot token:

    curl "https://api.telegram.org/botTOKEN/getMe"

Configure bot token:

    TELEGRAM_BOT_TOKEN=YOUR_TOKEN >> ~/.hermes/.env

Verify configuration:

    grep "TELEGRAM_BOT_TOKEN" ~/.hermes/.env

---

## 🚨 Troubleshooting

**Issue 1 — Clipboard Failure in VM**  
Problem: Unable to paste token in VirtualBox terminal  
Fix: Manual configuration via `.env` and `config.toml`

**Issue 2 — Invalid Token Error**  
Problem: `telegram.error.InvalidToken`  
Fix: Verified token directly via Telegram API curl call

**Issue 3 — Old Token Cached**  
Problem: Hermes loading outdated token from wrong config  
Fix: Updated token directly in `~/.hermes/.env`

---

## 🔍 Security Analysis Results

Test command sent via Telegram:

    analyze IP 10.0.2.15

| Finding | Result |
|---|---|
| External open ports | None detected ✅ |
| NAT environment | Confirmed |
| Externally exposed services | No ✅ |
| Local-only services | Yes ✅ |

| Service | Binding | Status |
|---|---|---|
| Ollama | 127.0.0.1:11434 | ✅ Local only |
| Neo4j HTTP | 127.0.0.1:7474 | ✅ Local only |
| Neo4j Bolt | 127.0.0.1:7687 | ✅ Local only |

---

## 🧠 Concepts Demonstrated

- Linux system administration
- Systemd service management
- API authentication & token management
- Telegram Bot API integration
- Network inspection & NAT analysis
- AI orchestration with local LLM
- Environment variable management
- Log analysis & debugging

---

## 🚀 Future Roadmap

- Nmap automated scanning via Telegram
- VirusTotal API integration
- Shodan OSINT queries
- Login attempt alerts to Telegram
- CVE analysis automation
- Threat intelligence summaries

---

## 💼 Portfolio Value

Demonstrates practical skills in SOC Operations, AI Integration,
Linux Administration, API Development, Debugging, and Infrastructure
management — suitable for SOC Analyst and Junior Cybersecurity roles.
