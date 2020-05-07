---
title: Setting up a new subdomain
description: Learn how to set up a new subdomain for your campaign instances
---

# Setting up a new subdomain {#setting-up-subdomain}

>[!CONTEXTUALHELP]
>id="cp_subdomain_management"
>title="Setup new subdomains and manage certificates"
>abstract="You need to setup a new subdomain and manage your subdomains' SSL certificates to start sending emails or publish landing pages with Adobe Campaign."
>additional-url="https://docs.adobe.com/content/help/en/control-panel/using/subdomains-and-certificates/monitoring-ssl-certificates.html" text="How to monitor your subdomains' SSL certificates"

>[!IMPORTANT]
>
>Subdomain delegation from the Control Panel is available in beta, and subject to frequent updates and modifications without notice.

## Full subdomain delegation {#full-subdomain-delegation}

Control Panel allows you to fully delegate a subdomain to Adobe Campaign. To do this, follow the steps below.

 >[!NOTE]
 >
 >If the selected instance has no previously configured subdomains, the first subdomain delegated to Adobe will become the **primary subdomain** for that instance, you will not be able to change it in the future.
 >
 >Reverse DNS records will be created for other subdomains using the primary subdomain. Reply-to, and bounce addresses for other subdomains will be generated from the primary subdomain.

1. In the **[!UICONTROL Subdomains & Certificates]** card, select the desired production instance, then click **[!UICONTROL Setup new subdomain]**.

    ![](assets/subdomain1.png)

    >[!NOTE]
    >
    >Subdomain delegation is available for **production** instances only.

1. Click **[!UICONTROL Next]** to confirm the full delegation method.

    ![](assets/subdomain3.png)

    >[!NOTE]
    >
    >[CNAME](#use-cnames) and custom methods are currently not supported by the Control Panel.

1. Create the desired subdomain and nameservers in the hosting solution used by your organization. To do this, copy-paste the Adobe Nameserver information displayed in the wizard. For more on how to create a subdomain in a hosting solution, refer to the [tutorial video](https://video.tv.adobe.com/v/30175).

    >[!IMPORTANT]
    >
    >When configuring nameservers, make sure you **never delegate your root subdomain to Adobe**. Otherwise, the domain will be able to work with Adobe only. Any other use will be impossible, like for example sending internal emails to your organization's employees.
    >
    >Moreover, **do not create a separate zone file** for this new subdomain.

    ![](assets/subdomain4.png)

    Once the subdomain is created with the corresponding Adobe nameserver information, click **[!UICONTROL Next]**.

1. Select the desired use case for the subdomain:

    * **Marketing communications**: communications that are intended for a commercial purpose. Example: sales email campaign.
    * **Transactional & operational communications**: transactional communications contain information aimed at completing a process that the recipient has started with you. Example: purchase confirmation, password reset email. Organizational communications relate to the exchange of information, ideas, and views within and outside the organization, with no commercial purpose.

    ![](assets/subdomain5.png)

    **Breaking down your subdomains according to use cases is a best practice for deliverability**. By doing so, the reputation of each subdomain is isolated and protected. For example, if your subdomain for marketing communications ends up being blacklisted by Internet Service Providers, your transactional communications subdomain will not be impacted, and will keep being able to send communications.

    **You can delegate a subdomains for both Marketing and Transactional use cases**:

    * For Marketing use cases, subdomains will be configured on **MID** (Mid sourcing) instances.
    * For Transactional use cases, subdomains will be configured on ALL **RT** (Message Center / Real-time messaging) instances to ensure connectivity. The subdomains will therefore operate with all your RT instances.

    >[!NOTE]
    >
    >If you are using Campaign Classic, Control Panel allows you to see what RT/MID instances are connected to the Marketing instance that you are working with. For more on this, refer to [this section](../../instances-settings/using/instance-details.md).

1. Enter the subdomain that you created into your hosting solution, then click **[!UICONTROL Submit]**.

    Make sure you fill in the **full name** of the subdomain to delegate. For example, to delegate the "usoffers.email.weretail.com" subdomain, type "usoffers.email.weretail.com".

    ![](assets/subdomain6.png)

1. Once the subdomain is submitted, the Control Panel will check that it correctly point to Adobe NS records and that the Start of Authority (SOA) record does not exist for this subdomain.

    >[!NOTE]
    >
    >Note that while subdomain delegation runs, other requests through the Control Panel will be entered into a queue and performed only after the Subdomain Delegation completes, to prevent any performance issues.

1. If the checks are successful, the Control Panel will start setting up the subdomain with DNS records, additional URLs, inboxes etc.

    Eventually, the Deliverability team will be notified about the new subdomain, in order to audit it. The audit process can take up to 3-10 business days after the subdomain has been delegated. The checks that are performed include feedback loops and spam complaint loops testing. We therefore do not recommend using the subdomain before the audit has been completed, as it could result in bad subdomain reputation.

    You can get more details on the configuration progress by clicking the **[!UICONTROL Process details]** button.

    ![](assets/subdomain7.png)

    >[!NOTE]
    >
    >In some cases, delegation goes through, but the subdomain may not be successfully verified. The subdomain will stay into the **[!UICONTROL Processing]** list with a job log providing information on the error. Contact Customer Care if you have trouble resolving the issue.

At the end of the process, the subdomains will be configured to work with your Adobe Campaign instance and the elements below will be created:

* **The subdomain with the following DNS records**: SOA, MX, CNAME(s), DKIM, SPF, TXT,
* **Additional subdomains** to host mirror, resource, tracking pages and domain key,
* **Inboxes**: Sender, Error, Reply-to.

    By default, the "Reply-to" inbox from the Control Panel is configured to clear emails and is not reviewable. If you want to monitor your "Reply-to" inbox for your marketing campaigns, do not use this address.

You can get more details on the subdomain by clicking the **[!UICONTROL Subdomain details]** and **[!UICONTROL Sender info]** buttons.

![](assets/detail_buttons.png)

![](assets/subdomain_details.png)

![](assets/sender_info.png)

## Use of CNAMEs {#use-cnames}

The use of CNAMEs for subdomain delegation is not supported through the Control Panel. To use this method, contact Adobe Customer Care.

**Related topics:**

* [Delegating subdomains (tutorial video)](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/control-panel/subdomain-delegation.html)
* [Subdomains branding](../../subdomains-certificates/using/subdomains-branding.md)
* [Monitoring your subdomains](../../subdomains-certificates/using/monitoring-subdomains.md)