## Playbook of bruteforcing the user account

This is playbook is used to handle the bruteforcing the user account event by performing some precaution steps.

**NSG (Network Security Group)** is the network security feature used in VM which manages the inbound and outbound traffic of the Virtual machine network.

**Aim** This playbook aims to block the ip address of the attacker who tries to bruteforce the user account by add their ip address to the inbound deny rules with higher priority and send the alert mail to the Admin.

## PlayBook Logic App

![Block_ip_playbook](/images/block_ip.png)

1. Parse the custom details from the incident data such as ip address of attacker, vm name, time ,etc.

2. Store the ip of the attacker in a variable for further usage.

3. Next configure the NSG security group by manually creating the new inbound rule (Block ip) with the priority of 100 and deny of the usage and add any dummy ip address.

4. In the logic app, send get request to NSG to fetch all the security rules.

5. Parse the array of ip addresses in the Block_ip security rule and store it the variable.

6. Perform union operation on array of receive ip with the attacker ip generated a new array .

7. Send the PUT request to the NSG to update the Block_IP rule to add a new ip which is attacker's IP.
   ```json
   {
   "properties": {
       "securityRules": [
       {
           "name": "Block_IP",
           "properties": {
           "protocol": "*",
           "sourceAddressPrefixes": @{variables('response')},
           "destinationAddressPrefix": "*",
           "access": "Deny",
           "destinationPortRange": "*",
           "sourcePortRange": "*",
           "priority": 130,
           "direction": "Inbound"
           }
       }
       ]
   },
   "location": "eastasia"
   }
   ```
8. Next Send the Mail to the Admin to notify the incident and the updated NSG rule

---
