# Microsoft-Sentinal-lab

This is the Sentinal lab Demonstration of trigger the security events from the azure virtual machine , get the log from the AMA (Azure Monitoring Agent) data collector and flag this as a incident. Create a automation rule to handle this incident with the playbook. Playbook is the logical app which is trigger when the incident is create and handle the situation by sending alert via outlook mail, take security action to mitigate the risk and send the review mail to the Admin.

# Architecture Diagram

![Diagram](/images/Sentinel-Architecture-Diagram.png)

# Setup for the project

[Initial Azure Setup](/Initial_Setup.md)

[Get Raw Data from the Virtual Machine](/Get_Logs_From_VM.md)

[Creating Incidents from the logs](/Creating_Incident.md)

[Writing Response Action for the Incident](/Creating_Playbook.md)

[Setting Trigger to run response when incident created](/Automation_rule.md)

[Output](/Outputs.md)
