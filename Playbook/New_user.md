# Playbook for New User Creation

This playbook is created to respond when a new user is add to the local group of the virtual machine.

**Aim** : To send the outlook mail to the admin notify about the incident.

## Playbook Logic App

![Diagram](/images/send-basic-mail.png)

1. Add an action Compose after the microsoft incident is created.
2. Parse the Entity for the raw data of the incident.
3. create the html tags for the entity (not really needed).
4. Create compose variable to better user of variable.
5. Create an action outlook (send a email v2) and establish the connection by signing in with the app's outlook account.
6. Set up the parameters such as TO, Subject and the body of the email.
