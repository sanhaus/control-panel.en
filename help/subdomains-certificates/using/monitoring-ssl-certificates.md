---
title: Monitoring subdomains' SSL certificates
description: Learn how to monitor your subdomains' SSL certificates
---

# Monitoring subdomains' SSL certificates {#monitoring-ssl-certificates}

The **[!UICONTROL Subdomains and Certificates]** card allows you to see which ones of your subdomains and associated subdomains hosting your landing pages and resources with SSL certificates installed on them.

You can also easily see which subdomains have expiring certificates and renew them if necessary.

>[!NOTE]
>
>Adobe recommends that you renew an SSL certificate of the associated subdomains **when it is close to the expiration date**. Certificate renewal can take a few days depending on your organization, we recommend that you allocate appropriate time for this process.
<!-- note to remove? immediate, no more delay? -->

The list of subdomains for each of your instances is accessible directly when selecting the **[!UICONTROL Subdomains & Certificates]** card.

Subdomains are arranged by the closest expiration date of the SSL certificate, with visual information on the expiration, in days:

* **Green**: the subdomain has not certificate expiring within the next 60 days.
* **Orange**: one or more subdomains has a certificate that will expire within the next 60 days.
* **Red**: one or more subdomains has a certificate that will expire within the next 30 days.

![](assets/visual_alert2.png)

To get more details on a subdomain's certificates, click the **[!UICONTROL Certificate Details]** button.

![](assets/certificate_details4.png)

The list of all related subdomains will be displayed on their certificates. It typically includes subdomains of landing pages, resource pages, etc.

![](assets/monitoring_subdomains_details2.png)

If necessary, you can initiate a certificate renewal request from this window. For more on this, refer to the section below.
