# IncidentUpdate -Get-SentinelAlertsEvidence

This playbook will run on a time schedule base (every hour) and it will check for any incident that was updated (in the last hour) in your Sentinel workspace by Sentinel Alerts. <br>
It will then automatically attach the new alert evidence from the updated Azure Sentinel incident (from the last hour) and send the evidence to an Event Hub that can be consumed by a 3rd party SIEM solution.


Author: Naomi Christis and Yaniv Shasha

Deploy the solution
1.	Create an Event Hub using the article "Create an event hub using Azure portal" <br>
https://docs.microsoft.com/en-us/azure/event-hubs/event-hubs-create  or use an existing Event Hub.

2.	Press the “deploy to azure” button:<br>
<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FNchristis%2FPlaybook%2Fmain%2FIncidentUpdate-GetSentinelAlertsEvidence.json" target="_blank">
    <img src="https://aka.ms/deploytoazurebutton"/>
</a>
<br>

3. Fill in the required parameters <br>
(the number of event you want to export to Event Hub (default value is 10 last events ) and the playbook name)

4.	Once the playbook is deployed; modify the required connection to Azure Monitor Logs (This means configuring the connection to your workspace so we can query for the updated Azure Sentinel incidents).<br>

5.	Next, configure the connection to your event hub (in the "send event" actions; use your Event Hub from step 1.) <br>



