---
title: Database monitoring
description: Learn how to monitor your Campaign database in the Control Panel
---

# Database monitoring {#database-monitoring}

## About instances databases {#about-instances-databases}

According to your contract, each of your Campaign instances is provisioned with a specific amount of database space.

Databases include all **assets**, **workflows** and **data** that is stored in Adobe Campaign.

Over time, databases can reach their maximum capacity, especially if the stored resources are never deleted from the instance, or if there are many workflows in a paused state.

Overflowing an instance database can lead to several issues (inability to login, to send emails etc.). Monitoring your instances' databases is therefore essential to ensure optimal performance.

>[!NOTE]
>
>Note that there may be some discrepancies between your current database space capacity and the amount specified in your contrat for distinct periods of time to ensure higher performance.

## Monitoring database usage {#monitoring-instances-database}

1. Open the **[!UICONTROL Health Monitoring]** card, then select the **[!UICONTROL Databases]** tab.

1. Select the desired instance from the **[!UICONTROL Instance List]**.

    The upper area provides information on the instance's database capacity and used space.

    ![](assets/databases_dashboard.png)

    The lower area provides a graphical representation of the database utilization over the last 7 days. You can change the displayed period of time using the available filters in the upper-right corner.

    Hovering over the graph allows you to get detailed information on the selected period of time.

    ![](assets/databases_dashboard_detail.png)

## Preventing database overload {#preventing-database-overload}

Campaign Standard and Classic offer various ways of preventing overconsumption of database disk space.

The section below provides useful resources from Campaign documentations to help you optimize your databases usage:

**Workflows monitoring**

* [Workflows best practices](https://docs.adobe.com/content/help/en/campaign-standard/using/managing-processes-and-data/workflow-general-operation/best-practices-workflows.html) (Campaign Standard)
* [Monitoring workflow execution](https://docs.adobe.com/help/en/campaign-classic/using/automating-with-workflows/monitoring-workflows/monitoring-workflow-execution.html) (Campaign Classic)

**Database maintenance**

* Database cleanup technnical workflow ([Campaign Standard](https://docs.adobe.com/help/en/campaign-standard/using/administrating/application-settings/technical-workflowshtml#list-of-technical-workflows) / [Campaign Classic](https://docs.adobe.com/help/en/campaign-classic/using/monitoring-campaign-classic/data-processing/database-cleanup-workflow.html))
* [Database maintenance guide](https://docs.adobe.com/content/help/en/campaign-classic/using/monitoring-campaign-classic/database-maintenance/recommendations.html) (Campaign Classic)
* [Database performance troubleshooting](https://docs.adobe.com/content/help/en/campaign-classic/using/monitoring-campaign-classic/troubleshooting/database-performances.html) (Campaign Classic)
* [Database-related options](https://docs.adobe.com/help/en/campaign-classic/using/installing-campaign-classic/appendices/configuring-campaign-options.html#database) (Campaign Classic)
