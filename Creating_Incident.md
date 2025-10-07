# Creating Incidents from the Logs

Our next stage is to create the incidents from the logs. This can be done by querying the logs with KQL.

We need to write an Analytic Rules to Create the incident from the raw logs.

---

## Steps to create the Incident

1. Go to our sentinel page and select the Analytics rule from the left side bar.
2. Create new Analytics Rules.
3. There are two types for Analytics Rule.

   - **Scheduled Rule** -> Runs only at the scheduled interval of time.
   - **Near Real time Rule** -> Runs for every time less than 1 minute (more consumption).

4. Select the Scheduled Rules.
5. Fix the related Mitre Attack and the severity level.
6. Write the Kusto Query Language which can easily parse the incident.
7. Set the time interval for which the query will be executed.
8. Set the time period for which the log data should be taken into account.

![Example_Incident](/images/brute_force_analytics_rule2.png)

---

## KQL queries for incidents

1. New User Creation

   ```KQL
   SecurityEvent
   | where EventID ==4720
   | project TimeGenerated, AccountCreated = TargetUserName, Computer, CreatedBy = SubjectUserName
   ```

2. BruteForcing on the VM

   ```KQL
   SecurityEvent
   | where EventID==4625
   | summarize FailedCount = count() by TargetUserName, IpAddress, Computer, bin(TimeGenerated,5m)
   | where FailedCount >= 3
   | project TimeGenerated = bin(TimeGenerated,5m) , TargetUser = TargetUserName, Computer, IpAddress, FailedCount
   ```

3. An User added to the Admin Group

   ```KQL
   SecurityEvent
   | where EventID ==4732  and TargetUserName == 'Administrators'
   | project TimeGenerated, Computer, AddedUser = MemberName, AddedSid = MemberSid, SubjectUserName
   ```

---
