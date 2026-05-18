# 🔍 Lab 02 — Port Scanning & Service Detection with Nmap

## Objective
Identify open ports, services and versions running on a target system.

## Tool
- Nmap 7.99

## Environment
- Kali Linux

## Commands Used
```bash
# Basic scan
nmap target.com

# Service version detection
nmap -sV --version-intensity 1 --open target.com

# Specific ports
nmap -Pn -sV -p 80,443,22 target.com

# Save results
nmap -sV --open target.com > results.txt
```

## Parameters Reference
| Parameter | Meaning |
|---|---|
| `-sV` | Service version detection |
| `-Pn` | Skip ping, assume host is up |
| `--open` | Show only open ports |
| `--version-intensity 1` | Light version detection |
| `>` | Redirect output to file |

## Target — scanme.nmap.org
| Port | State | Service | Version |
|---|---|---|---|
| 22/tcp | open | SSH | OpenSSH 6.6.1p1 Ubuntu |
| 80/tcp | open | HTTP | Apache 2.4.7 Ubuntu |
| 9929/tcp | open | nping-echo | Nping |

## Key Findings
- Apache 2.4.7 — outdated (2014), multiple CVEs found
- OpenSSH 6.6.1 — outdated (2014), vulnerable to username enumeration

## Lessons Learned
- Version detection reveals exploitable vulnerabilities
- Always cross-reference versions with Searchsploit
- Filtered ports indicate firewall protection
