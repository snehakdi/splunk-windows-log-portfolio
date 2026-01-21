# Network Traffic Analysis using Wireshark  

## Project Overview

This project focuses on analyzing real-world network traffic using Wireshark to understand communication patterns, identify encrypted traffic, and assess whether observed activity is benign or suspicious from a SOC analyst perspective.

The packet capture includes internal network communication and outbound encrypted web traffic over modern protocols.  

---

## Tools Used

Wireshark

---


## Key Findings  

  Screenshot1.Png

   - Identified UDP-based HTTPS traffic (port 443) indicating the use of QUIC / HTTP-3, commonly used by modern browsers and cloud services.

   - Observed TLS v1.2 encrypted application data, confirming secure communication and encrypted payloads.

  - Detected IPv6-based external communication, reflecting real-world dual-stack network environments.

   - Noted a TCP SYN request to port 9997 from an internal private IP, likely related to an internal application or service connectivity check.

   - No evidence of malicious activity such as port scanning, brute-force attempts, or command-and-control traffic was observed.

   - Traffic behavior was consistent with normal user and application activity.  
   

 Screenshot2.png

  - Packets 50–52 (IPv6 TLS Session): Ongoing encrypted communication between a local host and a remote server, characterized by "Application Data" exchanges and 
   TCP Acknowledgments.

  - Packets 53–54 (External TCP Maintenance): Background TCP traffic with a Google-owned server, maintaining a persistent connection.

  - Packet 55 (Connection Failure): A TCP Retransmission from 192.168.1.7 attempting to reach 192.168.1.6 on port 9997. The lack of a response triggers a timeout.

  - Packet 56 (Address Resolution): An ARP Request ("Who has?") triggered by the failed connection above. Device 1.7 is broadcasting to find the hardware (MAC) 
   address of 1.6 because it is no longer responding on the local network.

  - Packet 57 (Service Discovery): An SSDP M-SEARCH broadcast from 192.168.1.5, used to discover Plug-and-Play (UPnP) devices like printers or media servers.

  - Packets 58–61 (Cloudflare TLS Session): Successful encrypted data transfer between the local host and a Cloudflare-hosted service over HTTPS (Port 443).  
  


Screenshot3.png

  - Packet 479, 485–486 (QUIC Traffic): High-speed, encrypted UDP-based traffic (QUIC) is observed between a local host and a remote server. The "Protected 
    Payload" indicates data transfer within an established session, typically used for low-latency web applications.

  - Packet 480 (IGMPv2 Membership Query): The gateway (192.168.1.1) issued a General Query to the multicast address 224.0.0.1. This is a standard network 
    maintenance event where the router polls the local segment to identify which devices belong to specific multicast groups.

  - Packet 481–482 (TLS v1.2 Application Data): Encrypted application-layer data exchange between the IPv6 endpoints. This follows standard HTTPS/TLS behavior for 
    secure data transmission.

  - Packet 483 (TCP ACK): A standard TCP acknowledgement sent from the server (...:12) to the client, confirming receipt of the data transmitted in the previous 
    sequence.

  - Packet 484 (IGMPv2 Membership Report): In direct response to the query in packet 480, host 192.168.1.7 sent a Membership Report for the multicast group 
    239.255.255.250. This confirms that the host is active and wishes to continue receiving traffic for that group .  
