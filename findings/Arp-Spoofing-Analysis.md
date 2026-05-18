# ARP Spoofing Analysis

## Objective

Investigate suspicious ARP activity and possible Man-in-the-Middle behaviour.

## Filter Used

arp
arp.duplicate-address-detected

arp.duplicate-address-detected

## Findings

Wireshark detected a duplicate IP address conflict for 192.168.1.12.

Two different MAC addresses claimed ownership of the same IP address:

- 00:0c:29:e2:18:b4
- 00:0c:29:98:c7:a8

This behaviour is consistent with ARP spoofing activity used in Man-in-the-Middle attacks.

## Evidence

https://github.com/rodrigoguadano/Network-Traffic-Analysis-with-Wireshark/blob/5e1c45d78f91963c45f4309e1ab87667d0afe3a9/Screenshots/ARP-Spoof.png

## Conclusion

The capture contains indicators of ARP poisoning where a malicious host attempts to impersonate another device on the network.
