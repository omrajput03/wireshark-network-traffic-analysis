# Task 5 – Capture and Analyze Network Traffic Using Wireshark

## Objective
Capture live network packets and identify basic protocols and traffic types using Wireshark.

## Tool Used
- **Wireshark 4.6.3** (free, open-source packet analyzer)

## Steps Performed
1. Launched Wireshark and selected the active network interface.
2. Generated traffic by browsing websites and running `ping 8.8.8.8`.
3. Stopped capture after ~52 seconds (5541 packets captured).
4. Applied display filters (`dns`, `tcp`, `icmp`, `tls`, `quic`, `arp`) to analyze protocols.
5. Exported the capture as `capture.pcapng`.

## Protocols Identified

| Protocol | Frames | Description |
|----------|--------|-------------|
| **DNS** | 312 | Domain name resolution (UDP 53 + TCP) |
| **TCP** | 1566 | Reliable transport layer protocol |
| **TLS/HTTPS** | 107 | Encrypted web traffic over TCP 443 |
| **QUIC** | 2265 | Google's UDP-based encrypted transport |
| **ICMP** | 8 | Ping Echo Request/Reply to 8.8.8.8 |
| **ARP** | 4 | Local MAC address resolution |

## Sample DNS Queries Observed
- `accounts.youtube.com`
- `fonts.googleapis.com`
- `play.google.com`
- `edge.microsoft.com`

## Files in This Repository
- `capture.pcapng` – Raw Wireshark packet capture file
- `analysis_report.md` – Detailed protocol analysis report
- `README.md` – This file

## Wireshark Filters Used
```
dns
tcp
icmp
tls
quic
arp
ip.addr == 8.8.8.8
```
