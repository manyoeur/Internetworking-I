# Basic Cisco switch configuration
## 1. Enter Privileged Mode
```
Switch> enable
```
## 2. Enter Global Configuration Mode
```
Switch# configure terminal
```
## 3. Change the Hostname
```
Switch(config)# hostname SW1
```
## 4. Set Console Password
```

SW1(config)# line console 0
SW1(config-line)# password cisco123
SW1(config-line)# login
SW1(config-line)# exit
```
## 5. Set Enable (Privilege Mode) Password
```
SW1(config)# enable secret admin123
```
## 6. Create Management VLAN (Example: VLAN 10)
```

SW1(config)# vlan 1
SW1(config-vlan)# name MANAGEMENT
SW1(config-vlan)# exit
```
## 7. Configure VLAN Interface IP (SVI)
```
SW1(config)# interface vlan 1
SW1(config-if)# ip address 192.168.10.1 255.255.255.0
SW1(config-if)# no shutdown
SW1(config-if)# exit
```
## 8. Assign Management VLAN to Access Ports
```
SW1(config)# interface fastEthernet0/1
SW1(config-if)# switchport mode access
```
## 10. Configure Remote Management (Telnet + SSH)
### A. Enable Telnet (Not secure, used only for beginner labs)
```
SW1(config)# line vty 0 4
SW1(config-line)# password telnet123
SW1(config-line)# login
SW1(config-line)# exit
```
### B. Configure SSH (Recommended for security)
1. Set domain name
```
   SW1(config)# ip domain-name mynetwork.local
```
2. Generate RSA keys
```
SW1(config)# crypto key generate rsa
  How many bits? 2048
```
3. Create a local user account
```
SW1(config)# username admin privilege 15 password admin123
```
4. Enable SSH access
```

SW1(config)# line vty 0 4
SW1(config-line)# transport input ssh telnet
SW1(config-line)# login local
SW1(config-line)# exit
```
### 11. Save Configuration
```
SW1# write memory
```
or
```
SW1# copy running-config startup-config
```

SW1(config-if)# switchport access vlan 10
SW1(config-if)# exit
