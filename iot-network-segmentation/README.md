# IoT Network Segmentation Lab (GL.iNet Mango Mini)

## Overview
This project demonstrates the configuration of a segmented home network using a GL.iNet Mango Mini router. The goal was to separate trusted devices from IoT devices while maintaining internet access and enforcing network isolation.

---

## Objectives
- Create a primary trusted network (`devlan_main`)
- Create an isolated IoT network (`devlan_iot`)
- Ensure IoT devices have internet access only
- Prevent IoT devices from accessing the main LAN or router admin interface
- Validate network segmentation behavior

---

## Network Design

```
Internet
    |
GL.iNet Mango Mini (192.168.9.1)
    |
    ├── devlan_main (Trusted Devices)
    |      - Full LAN access
    |      - Router admin access
    |
    └── devlan_iot (IoT Devices)
           - Internet access only
           - No LAN or router access
```

---

## Configuration Summary

### Main Network
- SSID: `devlan_main`
- Role: Trusted devices
- Access: Full LAN + internet

### IoT Network
- SSID: `devlan_iot`
- Role: Untrusted / IoT devices
- Access: Internet only
- Restrictions: No LAN access, no router admin access

### Router LAN
- IP Address: `192.168.9.1`
- Subnet: `192.168.9.0/24`

---

## Validation Testing

### Test 1: Internet Connectivity
- Connected devices to both networks
- Verified internet access on:
  - `devlan_main`
  - `devlan_iot`

### Test 2: Network Isolation
- Attempted access from IoT network to LAN devices
- Verified IoT network cannot access:
  - Router admin interface (192.168.9.1)
  - Internal LAN devices

---

## Screenshots

### Router Dashboard
![Router Dashboard](screenshots/router-dashboard.png)

### Main WiFi Configuration
![Main WiFi](screenshots/devlan_main.png)

### IoT WiFi Configuration
![IoT WiFi](screenshots/devlan_iot.png)

### Client List
![Clients](screenshots/clients.png)

### Isolation Test (Optional)
![Isolation Test](screenshots/test.png)

---

## Skills Demonstrated
- Network segmentation
- Wireless configuration
- Basic firewall/isolation concepts
- LAN subnet configuration
- Troubleshooting WAN vs LAN connectivity
- Practical home lab networking

---

## Notes
This project simulates a real-world home or small office network design where IoT devices are isolated from trusted devices to improve security and reduce attack surface.
