# 🔍 Lab 03 — Disk Forensics with Autopsy

## Objective
Analyze a forensic disk image, recover deleted files and build a timeline
of events.

## Tool
- Autopsy 2.24

## Environment
- Kali Linux

## Commands Used
```bash
# Start Autopsy
sudo autopsy

# Create forensic image
dd if=/dev/zero of=practica.img bs=1M count=100

# Format image
mkfs.ext4 practica.img

# Mount image
sudo mount -o loop practica.img /mnt/forense

# Unmount image
sudo umount /mnt/forense

# Calculate MD5 hash
md5sum practica.img
```

## Case Details
| Field | Value |
|---|---|
| Case Name | Lab_Forense_01 |
| Investigator | mick-forensics |
| Image MD5 | A39A2BF523820E3F660E2F6A168D74DC |
| Integrity | PASS ✅ |

## Evidence Found
| # | File | Content | Status |
|---|---|---|---|
| 1 | transaccion.txt | Bank transfer $50,000 account 4829-1047 | Active |
| 2 | contactos.txt | criminal@darkweb.com - friday meeting | Active |
| 3 | claves.txt | Server credentials | Deleted — Recovered ✅ |

## Timeline of Events
| Time | Event |
|---|---|
| 19:42:32 | transaccion.txt created |
| 19:42:41 | contactos.txt created |
| 19:43:46 | claves.txt DELETED — evidence destruction attempt |

## Key Findings
- Recovered deleted file proving suspect attempted to destroy evidence
- MD5 hash verified — evidence integrity maintained for court
- Timeline shows deliberate deletion 74 seconds after file creation

## Lessons Learned
- Deleted files remain recoverable until overwritten
- MD5 hash is mandatory for chain of custody
- Event timeline is critical evidence in criminal cases
