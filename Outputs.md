# Outputs

## 1. New User Creation

When the new user is created in the VM Machine , and mail is send to the admin.

![Mail for new user](/images/mail-received.png)

---

## 2. Brute Force on User Account.

When the user tries to brute for the VM Machine with known creds, the attacker ip is blocklisted by adding in the inbound deny security rule (Block_ip) with high priority and the alert message is send to the admin.

![NSG_rule](/images/nsg_block_ip.png)

![Output Mail](/images/output2.png)
