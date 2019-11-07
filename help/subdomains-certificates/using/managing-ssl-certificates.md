---
title: Managing subdomains' SSL certificates
description: Learn how to monitor your subdomains' SSL certificates and initiate their renewal process
---

# Managing subdomains' SSL certificates {#managing-subdomains-ssl-certificates}

The **[!UICONTROL Subdomains and Certificates]** card allows you to see which ones of your subdomains and associated subdomains hosting your landing pages and resources with SSL certificates installed on them. You can also easily see which subdomains have expiring certificates so that you can anticipate their expiration.

If a certificate is about to expire, you can then initiate a Customer Care request with all required information to renew the certificate and ensure proper functioning of your instance.

>[!NOTE]
>
>Adobe recommends that you renew an SSL certificate of the associated subdomains **when it is close to the expiration date**. Certificate renewal can take a few days depending on your organization, we recommend that you allocate appropriate time for this process.

## Monitoring SSL certificates {#monitoring-ssl-certificates}

The list of subdomains for each of your instances is accessible directly when selecting the **[!UICONTROL Subdomains & Certificates]** card.

Subdomains are arranged by the closest expiration date of the SSL certificate, with visual information on the expiration, in days:

* **Green**: the subdomain has not certificate expiring within the next 60 days.
* **Orange**: one or more subdomains has a certificate that will expire within the next 60 days.
* **Red**: one or more subdomains has a certificate that will expire within the next 30 days.

    visual_alert2

To get more details on a subdomain's certificates, click the **[!UICONTROL Certificate Details]** button.

    certificate_details4

The list of all related subdomains will be displayed on their certificates. It typically includes subdomains of landing pages, resource pages, etc.

    monitoring_subdomains_details2

If necessary, you can initiate a certificate renewal request from this window. For more on this, refer to the section below.

## Initiating SSL certificates renewal {#initiating-ssl-certificate-renewal}

>[!NOTE]
>
>Control Panel does not automatically manage certificate renewal. It only allows you to **initiate the renewal process** by preparing the request to be sent to Adobe Campaign Customer Care.

The SSL certificate renewal process includes 3 steps:

1. **Generation of the Certificate Signing Request (CSR)**
    Adobe Customer Care generates a CSR for you, upon the request made via the Customer Care portal. You will need to provide some information required to generate the CSR (such as Common Name, Organization Name and address, etc.). In the Control Panel, you can see the list of the required items when initiating the renewal process. For more on this, refer to the section below.
1. **Purchase of the SSL certificate**
    Once the Customer Care generates the CSR, you can download it and purchase the SSL certificate with it from the Certificate Authority that your company approves.
1. **Installation of the SSL certificate**
    Once you purchase the SSL certificate, you need to provide it to the Adobe Customer Care. The Certificate will be installed, and you will see the updated expiration dates of the certificates in the Control Panel.

To initiate the SSL certificates renewal in the Control Panel, follow these steps:

1. Open the **[!UICONTROL Subdomains & Certificates]** card, then click the **[!UICONTROL Certificate details]** icon of the subdomain with expiring certificates.

    renewal1

1. The list of related subdomains displays. It usually includes subdomains of landing pages, resource pages, etc.
    Click the **[!UICONTROL Ticket Details]** button to initiate the certificates renewal process.

    renewal2

1. A form displays, with all the details required to renew your SSL certificate. Make sure you fill in the requested information fully and accurately (contact your internal team, Security and IT teams if necessary). Otherwise, a Certificate Signing Request cannot be generated, and you will not be able to renew the certificate.

    * **[!UICONTROL IMS Org]**: ID of your Organization.
    * **[!UICONTROL Instance]**: URL of the Campaign instance that is associated with the subdomain.
    * **[!UICONTROL Common name]**: This is typically a tracking subdomain URL, associated with the subdomain with the expiring certificate.
    * **[!UICONTROL Subdomains]**: Subdomains that are linked to the subdomain with an expiring certificate. If you want to apply a single SSL certificate to other subdomains, you can add them to this list. In that case, make sure that those subdomains are associated with the same IMS Org and Instance URL.

>[!CAUTION]
>
>The **[!UICONTROL IMS Org]** and **[!UICONTROL Instance]** fields are filled in automatically by the Control Panel and should not be modified.

    renewal3

    Once the form is completed, click the **[!UICONTROL Copy Details]** button to save the information to your Clipboard.

>[!NOTE]
>
>If you do not clear your browser history, the information you entered will be saved, enabling you to use it  to renew the certificate later on.

1. Click the **[!UICONTROL Log new ticket]** button. You are automatically redirected to Adobe Campaign Customer Care sign in page.

    renewal4

1. Sign in, then create a new Support ticket with the "SSL certificate CSR request" subject.
    Paste all information copied previously into the body of the ticket, then click Submit.

    >[!NOTE]
    >
    >If you do not have privileges to file support cases for your organization, please pass all information that you have copied to the Clipboard to your Support Contact and ask them to open a new Customer Care ticket for you.

**Related topics:**

* [Campaign Standard tutorial video](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/control-panel/managing-ssl-certificates.html)
* [Campaign Classic tutorial video](https://docs.adobe.com/content/help/en/campaign-learn/campaign-classic-tutorials/administrating/control-panel-acc/managing-ssl-certificates.html)
