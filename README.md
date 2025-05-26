# 🔍 Local Network Port Scanning and Packet Capture

## 🧰 Tools Used
- Nmap (Kali Linux)
- Wireshark
- GitHub

## 🎯 Objective
To scan a local subnet (192.168.254.0/24) for live hosts and open ports using Nmap, and analyze the traffic using Wireshark.

## ✅ Steps Performed

1. **Host Discovery**
```bash
nmap -sn 192.168.254.132
```
- Confirmed the host is alive.

2. **Full Subnet Port Scan**
```bash
nmap -sS 192.168.254.0/24
```
- Performed a SYN scan.
- Discovered multiple hosts and open ports like 135, 445, 902, etc.

3. **Wireshark Analysis**
- Captured traffic on `eth0`.
- Used filter: `tcp.flags.syn == 1 && tcp.flags.ack == 0`
- Verified Nmap was sending SYN packets to different ports.

## 🧪 Results
- Live hosts identified.
- Open ports on each host listed.
- Packet capture shows SYN scans were properly sent and recorded.

## 🔐 Security Learning
- Port scanning is a primary method in network reconnaissance.
- Open ports can expose vulnerable services.
- Wireshark confirms what traffic is leaving your system and reaching the network.

## 📸 Screenshots
- Nmap terminal output
- Wireshark SYN scan filter

## 📁 Files in Repo
- `ok.pcapng` - Packet capture of scan
- `screenshots/` - Terminal and Wireshark views
- `README.md` - Project explanation

## 🚀 How to Reproduce
1. Run Nmap with `-sS` option.
2. Capture with Wireshark on interface (`eth0`, `wlan0`).
3. Filter for SYN-only packets in Wireshark.