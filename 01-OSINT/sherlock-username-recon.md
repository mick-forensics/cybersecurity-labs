# 🔍 Lab 01 — Username OSINT Recon with Sherlock

## Objective
Find all social media accounts associated with a username using Sherlock.

## Tool
- Sherlock v0.16.0

## Environment
- Kali Linux

## Commands Used
```bash
# Install Sherlock
sudo apt install sherlock -y

# Basic search
sherlock username

# Search with timeout and save results
sherlock username --output results.txt --timeout 10
```

## Results
- Searched username: `test123`
- Platforms found: 222+
- Results saved to: `notas_personales/sherlock_test.txt`

## Key Findings
- Username present on GitHub, Steam, TikTok, YouTube, HackerOne
- Found on cybersecurity platforms: HackTheBox, CyberDefenders

## Lessons Learned
- Sherlock searches 300+ platforms simultaneously
- User-Agent helps identify the tool used in investigations
- Always save results for documentation
