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

1. Run Nmap scan against target
2. Save output to .txt file
3. Pass output to Ollama AI
4. AI generates security analysis
5. Save report to case folder

## Key Findings
- AI successfully analyzed Nmap scan results
- TinyLlama works with limited RAM (1-2GB)
- Local AI = no API limits, no internet required, private

## Limitations
- TinyLlama has limited accuracy on complex security analysis
- Llama3 requires 6GB+ RAM for better results
- CPU-only mode is slower than GPU acceleration

## Lessons Learned
- AI + Security tools is the future of automated pentesting
- Local models protect sensitive client data
- More RAM = better AI models = better analysis
