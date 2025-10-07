# Creating Response Action for the Incident

The main aim of the sentinel is to automatically response to for the known incident which reduces the manual checking.

After creating the incident, we need to create the response action need to do when the incident is created. For this stage we need to use the Azure Playbook. 

## Azure Playbook
An Azure Playbook is an automated workflow built using Azure Logic Apps that helps respond to security incidents automatically in Microsoft Sentinel.

## Steps to create a Playbook

1. Go to the sentinel portal.
2. Select the automation from the left side tab.
3. Create a new Playbook with when the incident is created.
4. A new Playbook is created. 
5. Go to the Active Playbooks and select the new one we have created.
6. Click and configure the Playbook.
7. It takes us to the Logic App designer.
8. Create the logic for the response.
![logic_app](/images/send-basic-mail.png)
9. Save the configuration.

---

## Logical App Design for Our Incidents
1. New User Creation -> [New_user_Playbook](/Playbook/New_user.md)
2. Brute Forcing on VM -> [Brute Force Playbook](/Playbook/Block_IP.md)

---
