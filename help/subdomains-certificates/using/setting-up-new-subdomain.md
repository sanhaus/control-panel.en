---
title: Setting up a new subdomain
description: Learn how to set up a new subdomain for your campaign instances
---

# Setting up a new subdomain {#setting-up-subdomain}

>[!NOTE]
>
>Subdomain delegation from the Control Panel is currently in beta, and subject to frequent updates and modifications without notification.

## Full subdomain delegation {#full-subdomain-delegation}

Control Panel allows you to fully delegate a subdomain to Adobe Campaign. To do this, follow these steps:

1. In the **[!UICONTROL Subdomains & Certificates]** card, select the desired production instance, then click **[!UICONTROL Setup new subdomain]**.

    ![](assets/subdomain1.png)

    >[!NOTE]
    >
    >Subdoman delegation is available for **production** instances only.

1. Click **[!UICONTROL Next]** to confirm the full delegation method.

    ![](assets/subdomain3.png)

    >[!NOTE]
    >
    >[CNAME](#use-cnames) and custom methods are currently not supported by the Control Panel.

1. Create the desired subdomain and nameservers in the hosting solution used by your organization. To do this, copy-paste the Adobe Nameserver information displayed in the wizard. For more on how to create a subdomain in a hosting solution, refer to the [tutorial video](https://video.tv.adobe.com/v/30175).

    >[!CAUTION]
    >
    >When configuring nameservers, make sure you **never delegate your root subdomain to Adobe**. Otherwise, the domain will be able to work with Adobe only. Any other use will be impossible, like for example sending internal emails to your organization's employees.

    ![](assets/subdomain4.png)

    Note that if you do not have any subdomain configured, the subdomain you are setting up will be considered as the **primary subdomain**. Inboxes (sender, error, reply-to addresses) will remain the same for all subdomains configured later on on this subdomain.

    Once the subdomain is created with the corresponding Adobe nameserver information, click **[!UICONTROL Next]**.

1. Select the desired use case for the subdomain:

    * **Marketing communications**: communications that are intended for a commercial purpose. Example: sales email campaign.
    * **Transactional & operational communications**: transactional communications contains information aimed at completing a process that the recipient has started with you. Example: purchase confirmation, password reset email. Organizational communications relates to the exchange of information, ideas, and views within and outside the organization, with no commercial purpose.

    >[!NOTE]
    >
    >Breaking down your subdomains according to use cases is a best practice for deliverability. By doing so, the reputation of each subdomain is isolated and protected.
    >
    >For example, if your subdomain for marketing communications ends up being blacklisted by Internet Service Providers, your transactional communications subdomain will not be impacted, and will keep being able to send communications.

    ![](assets/subdomain5.png)

1. Enter the subdomain that you created into your hosting solution, then click **[!UICONTROL Submit]**.

    >[!NOTE]
    >
    > Make sure you fill in the **full name** of the subdomain to delegate. For example, to delegate the "usoffers.email.weretail.com" subdomain, type "usoffers.email.weretail.com".

    ![](assets/subdomain6.png)

1. Once the subdomain is submitted, the Control Panel will check that it corrently point to Adobe NS records and that the Start of Authority (SOA) record does not exist for this subdomain.

1. If the checks are successfull, the Control Panel will start setting up the subdomain with DNS records, additional URLs, inboxes etc. You can get more details on the configuration progress by clicking the **[!UICONTROL Process details]** button.

    ![](assets/subdomain7.png)

    >[!NOTE]
    >
    >In some cases, delegation goes through but the subdomain may not be successfully verified. The subdomain will go direcly into the **[!UICONTROL Verified subdomains]** list with the **[!UICONTROL Unverified]** status and a job log providing information on the error. Contact Customer Care if you have trouble resolving the issue.
    >
    >Note that while subdomain delegation runs, other requests through the Control Panel will be entered into a queue and performed only after the Subdomain Delegation completes, to prevent any performance issues.

At the end of the process, the subdomains will be configured to work with your Adobe Campaign instance and the elements below will be created:

* **The subdomain** with the following **DNS records**: SOA, MX, CNAME(s), DKIM, SPF, TXT,
* **Additional subdomains** to host mirror, resource, tracking pages and domainkey,
* **Inboxes**: Sender, Error, Reply-to.

You can get more details on the subdomain by clicking the **[!UICONTROL Subdomain Details]** button.

![](assets/subdomain_details_general.png)

![](assets/subdomains_details_senderinfo.png)

>[!NOTE]
>
>Additionally to the processing stage, Adobe wil notify the deliverability team about the new subdomain in order to audit the subdomain that has been created. The audit process can take up to 3 days after the subdomain has been delegated.
>
>The checks that are performed include feedback loops and spam complaint loops testing. We therefore do not recommend using the subdomain before the audit has been completed, as it could result in bad subdomain reputatiion.

## Use of CNAMEs {#use-cnames}

The use of CNAMEs for subdomain delegation is not recommended by Adobe and not supported through the Control Panel. To use this method, contact Adobe Customer Care.
