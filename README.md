# CMPG325 – Iketsetseng Private School Network Project

## Project Information

**Student Name:** KHUMALO, N  
**Student Number:** 42606152  
**Module:** CMPG325  
**Project ID:** CMPG325-2026-022  
**Client ID:** CLI-022  
**Client:** Iketsetseng Private School  
**Location:** Mahikeng, South Africa  
**Addressing Block:** 192.168.21.0/24  

---

## 1. Project Overview

This project involves the design and implementation of a computer network for Iketsetseng Private School using Cisco Packet Tracer.

The network is designed to provide connectivity between different areas of the school while using VLAN segmentation, DHCP, DNS, routing, and secured wireless access.

The design also considers the client's requirement to accommodate an additional floor or area of the building.

---

## 2. Client Requirements

The network was designed to address the following requirements:

- Provide network connectivity for the school.
- Use the allocated address block `192.168.21.0/24`.
- Separate different types of network traffic using VLANs.
- Provide wireless connectivity for staff and students.
- Secure wireless networks using WPA2-PSK.
- Provide additional wireless coverage for the new floor/area.
- Provide DHCP for automatic IP address allocation.
- Provide local DNS services.
- Minimise unnecessary use of the limited and expensive Internet bandwidth.

---

## 3. Assigned Networking Challenge

### Wireless Security

The assigned networking challenge for this project is **wireless security**.

WPA2-PSK with AES encryption was implemented on the wireless access points. Separate SSIDs are used for the different wireless areas.

The implemented wireless networks include:

- `Iketsetseng-Staff`
- `Iketsetseng-Student`
- `Iketsetseng-Student-Floor2`

The additional-floor access point provides wireless coverage for the client's additional area.

---

## 4. Network Devices

The implemented network includes:

- **R1-Edge** – Router and inter-VLAN routing
- **SW-Core** – Core switch and VLAN management
- **SRV-DHCP-DNS** – DHCP/DNS server
- **AP-Staff** – Staff wireless access point
- **AP-Student** – Student wireless access point
- **AP-Additional-Floor** – Additional-floor wireless access point
- Wireless laptops/clients for testing

---

## 5. VLAN and IP Addressing

| VLAN | Name | Network | Default Gateway |
|---|---|---|---|
| 10 | Staff | 192.168.21.0/26 | 192.168.21.62 |
| 20 | Students | 192.168.21.64/26 | 192.168.21.126 |
| 30 | Admin-Servers | 192.168.21.128/27 | 192.168.21.158 |
| 99 | Management | 192.168.21.192/28 | 192.168.21.193 |

### Server

**SRV-DHCP-DNS**

- IP Address: `192.168.21.130`
- Subnet Mask: `255.255.255.224`
- Default Gateway: `192.168.21.158`
- DNS: `192.168.21.130`

---

## 6. Wireless Configuration

### Staff Wireless

**SSID:** `Iketsetseng-Staff`  
**Security:** WPA2-PSK  
**Encryption:** AES  

### Student Wireless

**SSID:** `Iketsetseng-Student`  
**Security:** WPA2-PSK  
**Encryption:** AES  

### Additional-Floor Wireless

**SSID:** `Iketsetseng-Student-Floor2`  
**Security:** WPA2-PSK  
**Encryption:** AES  

The same secured wireless configuration was applied to the additional-floor access point to provide coverage in the newly required area.

---

## 7. DHCP and DNS

DHCP is configured on the R1-Edge router to automatically provide IP addresses to clients in the different VLANs.

The following DHCP pools were configured:

- `STAFF_POOL`
- `STUDENT_POOL`
- `ADMIN_POOL`

The network also uses a local DNS server at `192.168.21.130`.

The DNS record:

`www.iketsetseng.local`

resolves to:

`192.168.21.130`

---

## 8. Testing and Verification

The network was tested using Cisco Packet Tracer.

Testing included:

- DHCP address allocation
- VLAN configuration
- Inter-VLAN connectivity
- Wireless connectivity
- WPA2 password authentication
- Additional-floor wireless connectivity
- Gateway connectivity
- DNS name resolution

Example successful client addresses included:

- Staff client: `192.168.21.11`
- Student client: `192.168.21.75`
- Additional-floor client: `192.168.21.77`

The additional-floor wireless client successfully received an IP address through DHCP and was able to communicate with its default gateway and the local DNS server.

An incorrect wireless password was also tested and the client was unable to connect until the correct WPA2-PSK password was entered.

---

## 9. Repository Contents

```text
CMPG325-Iketsetseng-Network-Project/
│
├── README.md
│
├── Packet-Tracer/
│   └── Iketsetseng-Network-Final.pkt
│
├── Documentation/
│   └── CMPG325_Network_Implementation_Documentation_FIXED.docx
│
├── Implementation/
│   ├── Wireless-Configuration.md
│   ├── VLAN-Configuration.md
│   └── IP-Addressing.md
│
└── Evidence/
    └── screenshots/
```

---

## 10. Conclusion

The completed Packet Tracer network implements the required network infrastructure for Iketsetseng Private School. The design uses VLAN segmentation, routing, DHCP, DNS, and secured wireless connectivity.

The wireless security challenge was addressed using WPA2-PSK with AES, while the additional-floor requirement was addressed by deploying an additional wireless access point.

The network configuration and testing evidence are included in this repository.


