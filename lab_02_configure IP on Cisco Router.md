# How to configure IP on Cisco Router
<img width="1115" height="732" alt="image" src="https://github.com/user-attachments/assets/b0186131-3bb3-4474-bf40-c53108f358c4" />


## Step 1: Enter Privileged EXEC Mode
```
Router> enable
```
## Step 2: Enter Global Configuration Mode
```
Router# configure terminal
```
## Step 3: Select the Interface GigabitEthernet 0/0/0
```
Router(config)# interface gigabitEthernet 0/0/0
```
## Step 4: Assign the IP Address and Subnet Mask
```
Router(config-if)# ip address 192.168.1.254 255.255.255.0
Router(config-if)# ipv6 address 2001:db8:1111:1111::1/64
```
## Step 5: Enable the Interface (No Shutdown)
```
Router(config-if)# no shutdown
```
## Step 6: Exit Interface Configuration
```
Router(config-if)# exit
```
## Step 7: Select the Interface GigabitEthernet 0/0/1
```
Router(config)# interface gigabitEthernet 0/0/0
```
## Step 8: Assign the IP Address and Subnet Mask
```
Router(config-if)# ip address 192.168.2.254 255.255.255.0
Router(config-if)# ipv6 address 2001:db8:1111:2222::1/64
```
## Step 9: Enable the Interface (No Shutdown)
```
Router(config-if)# no shutdown
```
## Step 10: Exit Interface Configuration
```
Router(config-if)# end
```

## Step 11: Save the Configuration
```
Router# write
```

## Full Example Configuration
```

Router> enable
Router# configure terminal
Router(config)# interface gigabitEthernet 0/0/0
Router(config-if)# ip address 192.168.1.245 255.255.255.0
Router(config-if)# ipv6 address 2001:db8:1111:1111::1/64
Router(config-if)# no shutdown
Router(config-if)# exit

Router(config)# interface gigabitEthernet 0/0/1
Router(config-if)# ip address 192.168.2.245 255.255.255.0
Router(config-if)# ipv6 address 2001:db8:1111:2222::1/64
Router(config-if)# no shutdown
Router(config-if)# exit
Router(config)# exit
Router# write memory
```
