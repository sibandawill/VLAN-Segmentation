# IP Addressing Scheme

## VLAN 10
- Network: 192.168.10.0/24
- Gateway: 192.168.10.1
- Subnet Mask: 255.255.255.0
- PC1: 192.168.10.2
- PC2: 192.168.10.3
## VLAN 20
- Network: 192.168.20.0/24
- Gateway:192.168.20.1
- Subnet Mask: 255.255.255.0
- PC3: 192.168.20.2
- PC4: 192.168.20.3
## VLAN 30
- Network: 192.168.30.0/24
- Gateway: 192.168.30.1
- Subnet Mask: 255.255.255.0
- PC5: 192.168.30.2
- PC6: 192.168.30.3
## VLAN 40
- Network: 192.168.40.0/24
- Gateway: 192.168.40.1
- Subnet Mask: 255.255.255.0
- PC7: 192.168.40.2
- PC8: 192.168.40.4
## Router Configuration (Cisco IOS CLI)
- Configured secret
- Hostname: R1
- Configure interface g0/0 to an IP Address
- Configured Subinterface. Example: interface g0/0.40   | encapsulation dot1Q 40 | ip address 192.168.40.1 255.255.255.0
- Configured Trunking on g0/0. Example interface f0/24 | switchport mode trunk (allows all vlans) | switchport mode trunk allowed vlan 10, 20, 30, 40
- Configured a DHCP pool for each VLAN and added a DNS server 8.8.8.8. Example: ip dhcp pool VLAN40 | network 192.168.40.0 255.255.255.0 | default-router 192.168.40.1 | dns server 8.8.8.8

## Switch Configuration (Cisco IOS CLI)
- Hostname: SW1
- Assigned each VLAN to switch. Example: vlan 40
- Assigned f0/24 and g0/1 to trunking mode.
- Assigned f0/1-4 to access mode and configured each interface to the proper vlan.

- Hostname: SW2
- Assigned each VLAN to switch. Example: vlan 40
- Assigned f0/24 to trunking mode.
- Assigned f0/1-4 to access mode and configured each interface to the proper vlan.

## PC Configuration
- Enabled DHCP on each endpoint from PC1-PC8