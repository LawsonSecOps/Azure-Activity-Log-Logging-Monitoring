## Azure-Activity-Log-Logging-Monitoring
![image](https://github.com/LawsonSecOps/Azure-Activity-Log-Logging-Monitoring/assets/167668407/8ef63232-b7c7-4e73-9e65-a722551ca3ca)
## Introduction
In a previous project, KAFFCO Estate, a fictional company, set up an Azure-based honeynet to entice hackers from the Internet. Log sources were gathered in a Log Analytics workspace, facilitating Microsoft Sentinel's ability to generate attack maps, alerts, and incidents. Initial security metrics were assessed over a 24-hour period within this vulnerable environment. Following this, security controls were introduced to fortify the environment, and metrics were reevaluated for another 24 hours.
Among the logs collected, Azure's Activity Log stood out. This log records data plane operations, capturing crucial details such as operation type, resource, time, caller, and status. Stored in Azure Monitor, these logs provide centralized access and management. Integration with monitoring tools enables the creation of customized dashboards, alerts, and compliance reports. To further analyse these logs, I will configure Azure Monitor to send the Activity Log to the Log Analytics workspace.
## Step-By-Step Configuration Of Azure Activity Log Logging
![image](https://github.com/LawsonSecOps/Azure-Activity-Log-Logging-Monitoring/assets/167668407/05175199-2c48-4c99-8836-dad640bf9275)
1.	From the Azure home page, search for Monitor in the search bar.
2.	Click to open The Monitor from the drop-down menu.
![image](https://github.com/LawsonSecOps/Azure-Activity-Log-Logging-Monitoring/assets/167668407/e89b1c15-5dc3-48d3-91fa-698d5181cb78)
3.	From the Monitor page
4.	Click Activity log and then.
5.	Click Export Activity Logs
![image](https://github.com/LawsonSecOps/Azure-Activity-Log-Logging-Monitoring/assets/167668407/4dd255a2-db24-4de8-88f8-ff48d2f80da4)

6.	From the Diagnostic setting page, select the appropriate Subscription. In this case, it is "KAFFCOEstateProject”.
7.	Click Add diagnostic setting to configure the Diagnostic setting.
8.	Give the Diagnostic setting a name by entering a name. In this case, it is "DS-Monitor”.
9.	Select from the Logs categories which log you want to collect EX: Administrative, Security, Service Health, Alerts, Recommendation, etc.
10.	Select the destination for the selected logs. In this case, They are sent to the Log Analytics workspace.
11.	Select the appropriate Subscription. In this case "KAFFCOEstateProject"
12.	Select the appropriate Logs Analytics workspace. In this case, "Log Analytics REP" which resides in the east US 2
13.	Click Save to create the Diagnostic setting for Azure Active Log.
![image](https://github.com/LawsonSecOps/Azure-Activity-Log-Logging-Monitoring/assets/167668407/06a7eff6-4681-4329-9545-2e5747116011)
14.	Shows a Diagnostic setting named DS-monitor.
## Test To Ensure The Logs Have Been Ingested Into The Logs Analytics Workspace
![image](https://github.com/LawsonSecOps/Azure-Activity-Log-Logging-Monitoring/assets/167668407/cbc6f9b6-b738-4319-ab17-9f2c5a16a140)

1.	From the Azure home page, search for Log Analytics workspace in the search bar
2.	Click to open the Log Analytics workspace from the drop-down menu.

![image](https://github.com/LawsonSecOps/Azure-Activity-Log-Logging-Monitoring/assets/167668407/e326339f-6dd4-4ebf-9882-1e8637f1b844)

3.	From the Log Analytics workspace page
4.	Click Logs to access the query page.
5.	Type AZURE Activity (AZURE Activity is the table created by the Activity log sent to the Log Analytics workspace where logs reside)
6.	Click Run to run the AZURE Activity query.
7.	The results of the query are populated in the Logs Analytics workspace.

![image](https://github.com/LawsonSecOps/Azure-Activity-Log-Logging-Monitoring/assets/167668407/9c00d948-ea1c-4044-b512-7bd843fa5833)

8.	Click the down arrow of a log for a more in-depth analysis of the log. i.e.: You will see the caller, Caller Ip Address, Event Submission Timestamp [UTC], etc, ...

## Conclusion
The setup of the diagnostic setting for Azure Monitor was executed successfully. Consequently, the Activity log is currently being ingested and stored within the specified Log Analytics workspace. This integration facilitates effortless monitoring of Azure Subscription-level logs, offering a comprehensive perspective on management and data plane operations throughout the entirety of the Azure environment.























