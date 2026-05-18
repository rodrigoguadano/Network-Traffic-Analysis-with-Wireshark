# Nmap Scan Analysis

## Objective

Identify network scanning activity using Wireshark.

## Filter Used

tcp.flags.syn==1 and tcp.flags.ack==0 and tcp.window_size > 1024

## Findings

Detected multiple TCP SYN packets originating from a single host targeting multiple ports.

### Suspicious Host

- Source IP: 10.10.60.7

### Destination IP

- 10.10.47.123

### Indicators

- Sequential port probing
- Multiple SYN packets
- TCP Connect Scan behaviour
- Possible use of Nmap

## Evidence

https://github.com/rodrigoguadano/Network-Traffic-Analysis-with-Wireshark/blob/4b28c2d65e8598a16f4527a7e58fe898e90ece3e/Screenshots/Nmap-Scan.png

## Conclusion

The traffic pattern strongly indicates TCP Connect scanning activity consistent with Nmap reconnaissance.
