---
title: Database monitoring
description: Learn how to monitor your Campaign database in the Control Panel
---

# Database monitoring {#database-monitoring}

## About instances database space {#about-instances-database-space}

According to your contract, each of your Campaign instances is provisioned with a specific amount of database space.

>[!NOTE]
>
>Note that there may be some discrepancies between your current database space and the amount specified in your contrat for distinct periods of time to ensure higher performance.

Campaign instances databases include all assets, workflows and data that is stored in Adobe Campaign.

Over time, the database of your instance can reach its maximum capacity, especially occur if the resources stored in the database (images, data, assets) are never deleted from the instance, or if there are many workflows in a paused state.

Overflowing an instance database can lead to several issues when working with your instance (inability to login, to send emails etc.). Monitoring the database space utilization is therefore essential for the good performance of your Campaign instances.

## Monitoring your instances' database {#monitoring-instances-database}

To monitor the database space utilization, follow these steps:

1. Open the **[!UICONTROL Health Monitoring]** card, then select the **[!UICONTROL Databases]** tab.

1. Select the desired instance from the **[!UICONTROL Instance List]** to display its dashboard.

    The upper area provides information on the used space and the provided space specified in your contract.

    ![](assets/databases_dashboard.png)

    The lower area provides a graphical representation of the database space utilization over the last 7 days. You can change the displayed period of time using the available filters in the upper-right corner.

    Hovering the graph allows you to display a more detailed information.

    ![](assets/databases_dashboard_detail.png)

