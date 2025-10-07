## Get Security Event from Virtual Machine.

First process is to get the security events from virtual Machine as a log so that we can parse it with KQL(Kusto Query Language) and manage Event. This can be done by using **Data Connector**.

## Data Connector

It is a bridge that collects and ingests data from different sources — like Azure services, Microsoft 365, firewalls, or third-party security tools — into Log Analytics Workspace, where Sentinel can analyze it.

In our project we going to use **Azure Monitoring Agent** which is used to get the security log from the Virtual Machine.

## Step

1. Go to the sentinel page.

2. Go to the Content Hub.

3. Download the Windows Security Events.

![Windows Security Events](/images/windows_sec.png)

4. Go to the Data Collector App and search for **Windows Security Event via AMA**.

5. Configure this Data Connector.

![AMA](/images/windows_sec_event_ama.png)

6. Open the Log and type the KQL to fetch the Security Event.

```kql
SecurityEvent
```

![SecurityLog](/images/sec_log_vm1.png)
