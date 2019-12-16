---
title: Setting up a new subdomain
description: Learn how to set up a new subdomain for your campaign instances
---

# Setting up a new subdomain {#setting-up-subdomain}

## Full subdomain delegation {#full-subdomain-delegation}

Control Panel allows you to fully delegate a subdomain to Adobe Campaign. To do this, follow these steps:

1. In the **[!UICONTROL Subdomains & Certificates]** card, select the desired production instance, then click **[!UICONTROL Setup new subdomain]**.

    >[!NOTE]
    >
    >Subdoman delegation is available for **production** instances only.

    ![](assets/subdomain1.png)

1. Click **[!UICONTROL Next]** to confirm the full delegation method.

    >[!NOTE]
    >
    >[CNAME](#use-cnames) and custom methods are currently not supported by the Control Panel.

    ![](assets/subdomain3.png)

1. Create the desired subdomain and nameservers in the hosting solution used by your organization. To do this, copy-paste the Adobe Nameserver information displayed in the wizard.

    For more on how to create a subdomain in a hosting solution, refer to this tutorial video.

    ![](assets/subdomain4.png)

    Once the subdomain is created with the corresponding Adobe nameserver information, click **[!UICONTROL Next]**.

1. Select the desired use case for the subdomain:

    * **Marketing communications**: communications that are intended for a commercial purpose. Example: sales email campaign.
    * **Transactional & operational communications**: transactional communications contains information aimed at completing a process that the recipient has started with you. Example: purchase confirmation, password reset email.
    
        Organizational communications relates to the exchange of information, ideas, and views within and outside the organization, with no commercial purpose.

    ![](assets/subdomain5.png)

    >[!NOTE]
    >
    >Breaking down your subdomains according this way is a best practice for deliverability. By doing so, the reputation of each subdomain is isolated and protected.
    >
    >For example, if your subdomain for marketing communications ends up being blacklisted by Internet Service Providers, your transactional communications subdomain will not be impacted, and will keep being able to send communications.

1. Enter the subdomain that you created into your hosting solution with the Adobe Nameserver information, then click **[!UICONTROL Submit]**.

    ![](assets/subdomain6.png)

    >[!NOTE]
    >
    > Make sure you fill in the **full** subdomain name to delegate For example, to delegate the "usoffers.email.weretail.com" subdomain, type "usoffers.email.weretail.com".

1. Once the subdomain is submitted, the Control Panel will check that it corrently point to Adobe NS records and that the Start of Authority (SOA) record does not exist for this subdomain.

1. If the checks are passed, the Control Panel will start setting up the subdomain with DNS records, additional URLs, inboxes etc.

You can get more details on the configuration progress at any time by clicking the **[!UICONTROL Process details]** button.

    ![](assets/subdomain7.png)

In the end of the process, the elements below have been created and the subdomains will be configured to work with your Adobe Campaign instance:

* **The subdomain** with the following DNS records: SOA, MX, CNAME(s), DKIM, SPF, TXT.
* **Additional subdomains** to host mirror, resource, tracking pages and domainkey
* **Inboxes**: Sender, Error, Reply-to

## Use of CNAMEs {#use-cnames}

The use of CNAMEs for subdomain delegation is not recommended by Adobe and not supported through the Control Panel. For more on this method, refer to [this page](https://helpx.adobe.com/campaign/kb/domain-name-delegation.html).
