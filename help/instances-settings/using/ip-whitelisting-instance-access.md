---
title: IP whitelisting
description: Learn more about IP whitelisting in Control Panel for instance access
---

# IP whitelisting {#ip-whitelisting}

## About IP whitelisting {#about-ip-whitelisting}

By default, your Adobe Campaign Classic instance is not accessible from various IP addresses.

If your IP address has not been whitelisted, you will not be able to login to the instance from this address. The same way, you may not be able to connect an API to your Message Center or Marketing instance if the IP address has not been whitelisted with the instance explicitly.

Control Panel allows you to set up new connections to your instances by whitelisting IP addresses ranges. To do this, follow the steps described below.

Once IP addresses whitelisted, you can create and link Campaign operators to them so that the users can access the instance.

## Best practices {#best-practices}

Make sure you follow the recommendations and limitations below when whitelisting IP addresses in the Control Panel.

* **Do not enable IP access to all Access Types** if you do not intend the IP address to connect to your RT servers, or AEM security zone.
* **If you temporarily enabled access to your instance for an IP address**, make sure to remove the IP addresses from the whitelisted IP addresses once you don't it need anymore to connect to your instance.
* **We do not recommend whitelisting IP addresses of public places** (airports, hotels, etc.). Please use your company VPN address to keep your instance secure at all times.

## Whitelisting IP addresses for Instance access {#whistelisting-ip-addresses}

To whitelist IP addresses, follow these steps:

1. Open the **[!UICONTROL Instances Settings card]** to access the IP whitelisting tab, then click **[!UICONTROL Add new IP Range]**.

    >[!NOTE]
    >
    >If the Instance Settings card is not visible on the homepage of the Control Panel, this means your IMS ORG ID is not associated with any Adobe Campaign Classic instances

    ![](assets/ip_whitelist_list1.png)

1. Fill in the information for the IP Range that you want to whitelist as described below.

    ![](assets/ip_whitelist_add1.png)

    * **[!UICONTROL Instance(s)]**: The instances to which the IP addresses will be able to connect. Several instances can be manipulated at the same time. For example, IP whitelisting can be performed on both Production and Stage instances through the same step.
    * **[!UICONTROL IP Range]**: The IP range that you want to whitelist, in the CIDR format. Note that an IP range cannot overlap an existing whitelisted range. In that case, first delete the range that contains the overlapping IP.

    >[!NOTE]
    >
    >CIDR (Classless Inter-Domain Routing) is the supported format when adding IP ranges with the Control Panel interface. The syntax consists of an IP address, followed by a '/' character, and a decimal number. The format and its syntax are fully detailed in [this article](https://whatismyipaddress.com/cidr).
    >
    >You can search on the internet for free online tools that will help you convert the IP range that you have in hand to CIDR format.

    * **!UICONTROL Label]**: The label that will display in the whitelisted IP addresses list.
    * **[!UICONTROL Name]**: The name has to be unique for the Access Type, Instance (in case of External API connection) as well as the IP address.

1. Specify the type of access that you want to grant to the IP addresses:

    * **[!UICONTROL Campaign Console Access]**: The IP addresses will be allowed to connect to the Campaign Classic Console. Note that Console access is enabled for Marketing instances only. Access to MID and RT instance is not permitted and therefore not enabled.
    * **[!UICONTROL AEM connection]**: The specified AEM IP addresses will be allowed to connect to the Marketing instance.
    * **[!UICONTROL External API connection]**: External APIs with the specified IP addresses will be allowed to connect to the Marketing and/or Message Center (RT) instance. Note that connection to the console of RT instances is not enabled.

    ![](assets/ip_whitelist_acesstype.png)

1. Click the **[!UICONTROL Save]** button. The IP Range is added to the list of whitelisted IP addresses.

    ![](assets/ip_whitelist_added.png)

To delete whitelisted IP ranges, select them then click the **[!UICONTROL Delete IP range]** button.

**Related topics:**
* [IP whitelisting (tutorial video)](https://docs.adobe.com/content/help/en/campaign-learn/campaign-classic-tutorials/administrating/control-panel-acc/ip-whitelisting.html)
* [Linking a security zone to an operator](https://docs.campaign.adobe.com/doc/AC/en/INS_Additional_configurations_Configuring_Campaign_server.html#Linking_a_security_zone_to_an_operator)
