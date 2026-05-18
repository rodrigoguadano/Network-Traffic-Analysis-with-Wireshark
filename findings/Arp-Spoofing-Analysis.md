# ARP Spoofing Analysis

## Objective

Investigate suspicious ARP traffic and identify possible Man-in-the-Middle (MITM) activity within the network capture.

## Filters Used

```text
arp
arp.opcode == 2
arp.duplicate-address-detected
```

## Findings

Wireshark detected duplicate IP address conflicts indicating possible ARP poisoning activity.

### Duplicate IP Address Detected

The following alert was identified:

```text
Duplicate IP address detected for 192.168.1.12
(00:0c:29:e2:18:b4) - also in use by
00:0c:29:98:c7:a8
```

This indicates that two different MAC addresses attempted to claim ownership of the same IP address.

## Gateway Spoofing Detection

A second alert was detected involving the network gateway address:

```text
Duplicate IP address detected for 192.168.1.1
(00:0c:29:e2:18:b4) - also in use by
50:78:b3:f3:cd:f4
```

### Legitimate Gateway

- IP Address: 192.168.1.1
- MAC Address: 50:78:b3:f3:cd:f4

### Suspicious Host

- MAC Address: 00:0c:29:e2:18:b4

The suspicious host attempted to impersonate the default gateway in order to redirect network traffic.

## Indicators of Compromise

- Duplicate ARP replies
- Multiple MAC addresses claiming the same IP
- Gateway impersonation
- Abnormal ARP behaviour
- Potential traffic interception attempt

## Evidence

![ARP Spoofing](../screenshots/arp-spoof.png)

## Conclusion

The packet capture contains strong indicators of ARP spoofing and Man-in-the-Middle activity.

The host with MAC address `00:0c:29:e2:18:b4` attempted to impersonate both a victim host and the network gateway (`192.168.1.1`), which could allow the attacker to intercept, monitor or manipulate network communications.
