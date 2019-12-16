---
title: Monitoring subdomains' SSL certificates
description: Learn how to monitor your subdomains' SSL certificates
---

# Monitoring subdomains' SSL certificates {#monitoring-ssl-certificates}

## About SSL certificates {#about-ssl-certificates}

Adobe Campaign recommends that you secure the subdomains that host your landing pages, especially those that are gathering sensitive information of your customers.

**SSL (Secure Socket Layer) encryption** ensures that the subdomains that you delegated to Adobe are secure. When your customer fills out a web form or visits a landing page hosted by Adobe Campaign, by default the information is sent over non-secure protocol (HTTP). To ensure additional security, secure sent information with a HTTPS protocol. For example, your "http://info.mywebsite.com/" subdomain address will now be "https://info.mywebsite.com/".

**SSL certificates are not installed on the delegated subdomains themselves**. They are installed on associated subdomains, mainly those that host landing pages, resource pages and others.

**SSL certificates are provided for a specific period of time** (1 year, 60 days, etc.). Once a certificate expires, you may experience issues when accessing the landing pages or using resources from the subdomain. To prevent this, the Control Panel allows you to monitor your subdomains' SSL certificates, as well as initiate their renewal process.

![](assets/no_certificate.png)

## Monitoring your subdomains {#monitoring-your-subdomains}

The **[!UICONTROL Subdomains and Certificates]** card allows you to see which ones of your subdomains and associated subdomains hosting your landing pages and resources have SSL certificates installed on them.

You can also easily see which subdomains have expiring certificates and renew them if necessary.

>[!NOTE]
>
>Adobe recommends that you renew an SSL certificate of the associated subdomains **when it is close to the expiration date**. Certificate renewal can take a few days depending on your organization, we recommend that you allocate appropriate time for this process.

The list of subdomains for each of your production instances is accessible directly when selecting the **[!UICONTROL Subdomains & Certificates]** card.

Subdomains are arranged by the closest expiration date of the SSL certificate, with visual information on the expiration, in days:

* **Green**: the subdomain has not certificate expiring within the next 60 days.
* **Orange**: one or more subdomains has a certificate that will expire within the next 60 days.
* **Red**: one or more subdomains has a certificate that will expire within the next 30 days.
* **Grey**: no certificate has been installed on the subdomain.

![](assets/subdomains_list.png)

To get more details on a subdomain, click the **[!UICONTROL Subdomain Details]** button.
The list of all related subdomains displays. It typically includes subdomains of landing pages, resource pages, etc.

The **[!UICONTROL Sender info]** tab provides information on the configured inboxes (Sender, Reply to, Error email).
 
![](assets/subdomain_details.png)

In the subdomains list, the **[!UICONTROL Last verification]** column indicates when the subdomain was verified for the last time. You can launch a verification at any time by clicking the **...** / **[!UICONTROL Verify subdomain]** button.

>[!CAUTION]
>
>Adobe does not recommend using subdomains with no verificate date as it could mean that these subdomains may be having some deliverability issues.

![](assets/subdomain_verification.png)

When launching a verification, several operations are performed to check that the subdomain is correctly configured:

1. The Control Panel checks that the subdomain belongs to the instance tenant.
1. An email is sent from the instance using that subdomain to a set of test recipients of "250ok" (a third party email analytics and deliverability platform).
1. After receiving the email, 250ok reads the email headers and checks if the SPF and DKIM are setup and valid.
1. Control Panel continuously polls the delivery status from 250ok for around 20 minutes. If the SPF and DKIM passes, it means that the requested subdomain is verified and is fully configured and ready to use for sending emails.
