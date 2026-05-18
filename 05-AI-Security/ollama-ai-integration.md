# 🤖 Lab 05 — AI Integration with Security Tools using Ollama

## Objective
Integrate local AI models with cybersecurity tools to automate analysis
and generate security reports.

## Tools
- Ollama
- TinyLlama
- Nmap
- Nikto

## Environment
- Kali Linux

## Installation
```bash
# Install Ollama
curl -fsSL https://ollama.com/install.sh | sh

# Download model
ollama pull tinyllama

# Verify installation
ollama list
```

## Commands Used
```bash
# Run AI with direct prompt
ollama run tinyllama "Your prompt here"

# AI analyzes Nmap results
ollama run tinyllama "Analyze this scan: $(cat nmap_results.txt)"

# AI analyzes Nikto results
ollama run tinyllama "Analyze web vulnerabilities: $(cat nikto_results.txt)"
```

## AI Models Reference
| Model | Size | RAM Required | Quality |
|---|---|---|---|
| TinyLlama | 637MB | 1-2GB | Basic |
| Llama3 | 4.7GB | 6GB+ | Good |
| Mistral | 4.1GB | 6GB+ | Good for code |

## Workflow
