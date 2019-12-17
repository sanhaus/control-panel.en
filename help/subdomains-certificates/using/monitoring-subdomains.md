---
title: Monitoring subdomains' SSL certificates
description: Learn how to monitor your subdomains' SSL certificates
---

# Monitoring your subdomains {#monitoring-subdomains}

It is essential to monitor your subdomains to ensure that are all configured properly to work with Adobe Campaign.

The list of subdomains for each of your production instances is accessible directly when selecting the **[!UICONTROL Subdomains & Certificates]** card.

![](assets/subdomains_list.png)

To get more details on a subdomain, click the **[!UICONTROL Subdomain Details]** button.
The list of all related subdomains displays. It typically includes subdomains of landing pages, resource pages, etc.

The **[!UICONTROL Sender info]** tab provides information on the configured inboxes (Sender, Reply to, Error email).
 
![](assets/subdomain_details.png)


In the subdomains list, the **[!UICONTROL Last verification]** column indicates when a subdomain was verified for the last time. You can launch a verification at any time by clicking the **...** / **[!UICONTROL Verify subdomain]** button.

>[!CAUTION]
>
>Adobe does not recommend using subdomains with no verificate date as it could mean that these subdomains may be having some deliverability issues.

![](assets/subdomain_verification.png)

When launching a verification, several operations are performed to check that the subdomain is correctly configured:

1. The Control Panel checks that the subdomain belongs to the instance tenant.
1. An email is sent from the instance using that subdomain to a set of test recipients of "250ok" (a third party email analytics and deliverability platform).
1. After receiving the email, 250ok reads the email headers and checks if the SPF and DKIM are setup and valid.
1. Control Panel continuously polls the delivery status from 250ok for around 20 minutes. If the SPF and DKIM passes, it means that the requested subdomain is verified and is fully configured and ready to use for sending emails.
