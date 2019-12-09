---
title: Setting up a new subdomain
description: Learn how to set up a new subdomain for your campaign instances
---

# Setting up a subdomain {#setting-up-subdomain}

Control Panel allows you to fully delegate a subdomain to Adobe Campaign. To do this, follow the steps detailed below.

>[!NOTE]
>
>The use of CNAMEs for subdomain delegation is not supported through the Control Panel. For more on this method, refer to [this page](https://helpx.adobe.com/campaign/kb/domain-name-delegation.html).

1. In the **[!UICONTROL Subdomains & Certificates]** card, select the desired instance, then click the **[!UICONTROL Setup new subdomain]** button.

    ![](assets/subdomain1.png)

    >[!NOTE]
    >
    >The **[!UICONTROL Setup new subdomain]** button is available for Production instances only.

1. Select the **[!UICONTROL Delegation to Adobe]** method, then click **[!UICONTROL Next]**.

    ![](assets/subdomain3.png)

1. Create the desired subdomain in the hosting solution used by your organization. To do this, copy the Adobe Nameserver information displayed in the wizard, then paste it into your hosting solution.

    For more on how to create a subdomain in a hosting solution, refer to the tutorial video accessible from the wizard.

    ![](assets/subdomain4.png)

    Once the subdomain is created with the corresponding Adobe nameserver information, click **[!UICONTROL Next]**.

1. Select the desired use case for the subdomain:

    * **Marketing communications**: communications that are intended for a commercial purpose. Example: sales email campaign.
    * **Transactional & operational communications**: transactional communications contains information aimed at completing a process that the recipient has started with you. Example: purchase confirmation, password reset email. Organizational communications relates to the exchange of information, ideas, and views within and outside the organization, with no commercial purpose.

    Breaking down your subdomains according this way is a best practice for deliverability. By doing so, the reputation of each subdomain is isolated and protected. For example, if your subdomain for marketing communications ends up being blacklisted by Internet Service Providers, your transactional communications subdomain will not be impacted, and will keep being able to send communications.

    ![](assets/subdomain5.png)

    >[!NOTE]
    >
    >You can only select a use case that has been configured for your instance. If the instance has been configured for "Marketing communications" only, you will not be able to select the "Transactional & operation communications" use case.

1. Enter the subdomain that you created into your hosting solution with the Adobe Nameserver information, then click **[Submit]**.

    >[!NOTE]
    >
    > Make sure you fill in the **full** subdomain to delegate. For example, to delegate the "usoffers.email.weretail.com" subdomain, type "usoffers.email.weretail.com".

    ![](assets/subdomain6.png)

1. Once the subdomain is submitted, the Control Panel will perform various operations to configure the subdomain and check that it correctly points to the Campaign instance (namespace records creation, Campaign instance configuration, Start of Authority record verification, etc.).

    You can get more details on the configuration progress at any time by clicking the **[!UICONTROL Process details]** button.

    ![](assets/subdomain7.png)

What do you get in the end of the process?
* Subdomain with the following DNS records - SOA, MX, CNAME(s), DKIM, SPF, TXT. 
* Additional subdomains to host mirror, resource, tracking pages and domainkey
* Inboxes - Sender, Error, Reply-to
* Ultimately the subdomains will be configured to work with your Adobe Campaign instance
