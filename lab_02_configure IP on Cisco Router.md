# How to configure IP on Cisco Router
<img width="1003" height="716" alt="image" src="https://github.com/user-attachments/assets/cc7b3cbe-ea5b-49bc-8e7a-b5598978b366" />
<img width="1003" height="716" alt="image" src="https://github.com/user-attachments/assets/cc7b3cbe-ea5b-49bc-8e7a-b5598978b366" />

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
```
## Step 5: Enable the Interface (No Shutdown)
```
Router(config-if)# no shutdown
```
## Step 6: Exit Interface Configuration
```
Router(config-if)# end
```

## Step 7: Save the Configuration
```
Router# write
```
# Do the same for interface GigabitEthernet 0/0/1

## Full Example Configuration
```

Router> enable
Router# configure terminal
Router(config)# interface gigabitEthernet 0/0/0
Router(config-if)# ip address 192.168.1.245 255.255.255.0
Router(config-if)# no shutdown
Router(config-if)# exit

Router(config)# interface gigabitEthernet 0/0/1
Router(config-if)# ip address 192.168.2.245 255.255.255.0
Router(config-if)# no shutdown
Router(config-if)# exit
Router(config)# exit
Router# write memory
```
