---
title: Monitoring subdomains' SSL certificates
description: Learn how to monitor your subdomains' SSL certificates
---

# Monitoring your subdomains {#monitoring-subdomains}

It is essential to monitor your subdomains to ensure that are all configured properly to work with Adobe Campaign.

The list of subdomains for each of your production instances is accessible directly when selecting the **[!UICONTROL Subdomains & Certificates]** card.

![](assets/subdomains_list.png)

In the subdomains list, the **[!UICONTROL Last verification]** column indicates when a subdomain was verified for the last time. You can launch a verification at any time by clicking the **...** / **[!UICONTROL Verify subdomain]** button.

![](assets/subdomain_verification.png)

>[!CAUTION]
>
>Adobe does not recommend using subdomains with no certificate date as it could mean that these subdomains may be having some deliverability issues.

When launching a verification, several operations are performed to check that the subdomain is correctly configured (instance tenant check, email sending test, etc.)

If the subdomain's verification fails, contact Adobe Customer Care for further investigation.
