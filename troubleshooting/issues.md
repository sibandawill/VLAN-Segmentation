## Problems I came against creating this lab

- Trunking issue: DHCP was not reaching SW2, so all the devices connected to it could not have their IP address dynamically assigned
- Fix Attempt 1: Enabled switchport trunk mode on the f0/24 interfaces of SW1 and SW2.
- Fix Attempt 2: Added VLAN 10 and 40 to SW1. They were not defined, so they could not pass through because it did not exist. (This Worked)
Lesson: Each switch must have every VLAN configured even if it is not directly connected to a device that is on that specific VLAN.