# How to configure NAT-router
![GitHub Logo](https://www.manageengine.com/network-configuration-manager/images/static-NAT.jpg)

To configure static NAT on Cisco devices, following steps are required:
1. Configure private/public IP address mapping by using the ip nat inside source static PRIVATE_IP PUBLIC_IP command
2. Configure the router’s inside interface using the ip nat inside command
3. Configure the router’s outside interface using the ip nat outside command

Steps to configure static NAT on Cisco devices through CLI
Login to the device using SSH / TELNET and go to enable mode.
Go into the config mode.
Router#configure terminal

Enter configuration commands, one per line. End with CNTL/Z.

Router(config)#

Use below command to configure static NAT
`` Router(config)#ip nat inside source static 10.0.0.2 59.40.40.1 ``

Configure the router's inside interface
`` Router(config)# `` interface fa0/0

`` Router(config-if)#`` ip nat inside 

`` Router(config-if)# `` exit

Configure the router's outside interface
`` Router(config)#`` interface fa0/1

`` Router(config-if)# `` ip nat outside

`` Router(config-if)#`` exit

Exit config mode
`` Router(config)#`` exit

`` Router# ``

Execute show ip nat translations command to view the NAT configuration.
Copy the running configuration into startup configuration using below command
`` Router# `` write memory

Building configuration... [OK]

`` Router# ``
