# How to Configure SSH on a Cisco Switch
## 1️⃣ Set a Hostname
```
Switch(config)# hostname SW1
```
## 2️⃣ Configure a Domain Name
```
SW1(config)# ip domain-name yoeurman.com
```
## 3️⃣ Generate RSA Key Pair (for SSH Encryption)
```
SW1(config)# crypto key generate rsa
```
When prompted:
```
How many bits in the modulus [512]: 1024
```
## 4️⃣ Create a Local User for SSH Login
```
SW1(config)# username admin privilege 15 secret P@ssw0rd
```
## 5️⃣ Enable SSH on VTY Lines
```
SW1(config)# line vty 0 15
SW1(config-line)# transport input ssh
SW1(config-line)# login local
SW1(config-line)# exit
```
## 6️⃣ Specify SSH Version 2
```
SW1(config)# ip ssh version 2
```
## 8️⃣ Assign an IP Address to a VLAN Interface
```
SW1(config)# interface vlan 1
SW1(config-if)# ip address 192.168.1.10 255.255.255.0
SW1(config-if)# no shutdown
```
## 9️⃣ Add Default Gateway (If needed)
```
SW1(config)# ip default-gateway 192.168.1.1
```
✅ Test SSH From PC
```
ssh -l admin 192.168.1.10
```
