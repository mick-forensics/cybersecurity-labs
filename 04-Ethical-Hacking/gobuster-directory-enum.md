# 🔍 Lab 04 — Directory Enumeration with Gobuster

## Objective
Discover hidden directories and files on a web server using brute force.

## Tool
- Gobuster 3.8.2

## Environment
- Kali Linux

## Commands Used
```bash
# Basic directory scan
gobuster dir -u http://target.com -w /usr/share/wordlists/dirb/common.txt

# Save results
gobuster dir -u http://target.com -w /usr/share/wordlists/dirb/common.txt -o results.txt
```

## Parameters Reference
| Parameter | Meaning |
|---|---|
| `dir` | Directory enumeration mode |
| `-u` | Target URL |
| `-w` | Wordlist path |
| `-o` | Output file |

## HTTP Status Codes
| Code | Meaning |
|---|---|
| `200` | File exists and accessible |
| `301` | Redirects to another URL |
| `403` | Exists but access denied |
| `404` | Not found |

## Target — scanme.nmap.org
| Path | Status | Risk |
|---|---|---|
| `.svn` | 301 | 🔴 Critical — exposed repository |
| `.htpasswd` | 403 | 🔴 High — password file exists |
| `.htaccess` | 403 | ⚠️ Medium — config file |
| `shared/` | 301 | ⚠️ Medium — exposed folder |
| `images/` | 301 | ✅ Normal |

## Key Findings
- `.svn` repository exposed — may contain source code and credentials
- `.htpasswd` confirmed — password file present on server

## Lessons Learned
- Hidden directories often contain sensitive information
- `.svn` exposure is a critical finding in real pentest reports
- Always wordlist with common.txt first then escalate
