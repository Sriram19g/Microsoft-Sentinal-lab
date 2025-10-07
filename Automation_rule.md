# Linking the Response with the Incident

The last stage of the project is to link the response created in playbook with the incident trigger. We need to write the automation rule which triggers the particular response (playbook) when the particular incident is triggered.

## Step to create Automation Rule:

1. Go to Automation tab and create the automation rule.
2. Give a name for the automation rule.
3. Next set the trigger point.
   **Eg**:
   ```
   if analytic_rule contains (incident1, incident2, ...)
   ```
4. Set the response/ action to be perform.

   - Run a playbook -> select the particular playbook
   - Assign the incident to someone in the organization
   - Change the severity level
   - Change the status of the incident -> (New, Active, Closed)

5. Save this automation rule.

![Automation Rule](/images/automation_rule.png)
