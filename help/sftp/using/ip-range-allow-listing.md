---
title: IP range allow listing
description: Learn how to add IP ranges to the allow list for SFTP servers access
---

# IP range allow listing {#ip-range-whitelisting}

>[!CONTEXTUALHELP]
>id="cp_ip_whitelist"
>title="About IP allow listing"
>abstract="In this tab, you can add IP ranges to the allow list, in order to establish a connection to your SFTP servers. Only SFTP servers that you have access to are shown here. Please contact your Administrator to request access to other SFTP servers."
>additional-url="https://images-tv.adobe.com/mpcv3/8a977e03-d76c-44d3-853c-95d0b799c870_1560205338.1920x1080at3000_h264.mp4#t=98" text="Watch demo video"

SFTP servers are protected. In order to be able to access them in order to view files or write new ones, you need to add the public IP address of the system or client that accesses the servers to the allow list.

## About the CIDR format {#about-cidr-format}

CIDR (Classless Inter-Domain Routing) is the supported format when adding IP ranges with the Control Panel interface.

The syntax consists of an IP address, followed by a '/' character, and a decimal number. The format and its syntax are fully detailed in [this article](https://whatismyipaddress.com/cidr).

You can search on the internet for free online tools that will help you convert the IP range that you have in hand to CIDR format.

## Best practices {#best-practices}

Make sure you follow the recommendations and limitations below when adding IP addresses to the allow list in the Control Panel.

* **Add IP ranges to the allow list** rather than single IP addresses. To add a single IP address to the allow list, append a '/32' to it to indicate that the range only includes a single IP.
* **Do not add very wide ranges to the allow list**, for example including > 265 IP addresses. The Control Panel will reject any CIDR-format ranges that are between /0 and /23.
* Only **public IP addresses** can be added to the allow list.
* Make sure to **regularly delete IP addresses** that you don't need anymore from the allow list.

## Adding IP addresses to the allow list {#adding-ip-addresses-allow-list}

>[!CONTEXTUALHELP]
>id="cp_sftp_iprange_add"
>title="Add New Ip Range"
>abstract="Define the IP ranges that you want to add to the allow list in order to connect to your SFTP servers."

To add an IP range to the allow list, follow these steps:

1. Open the **[!UICONTROL SFTP]** card, then select the **[!UICONTROL IP Whistelisting]** tab.
1. The list of IP addresses on the allow list displays for each instance. Select the desired instance from the left-hand side list, then click the **[!UICONTROL Add new IP range]** button.

    ![](assets/control_panel_add_range.png)

1. Define the IP Range that you want to add to the allow list, in the CIDR format, then define the label that will display in the list.

    >[!NOTE]
    >
    >These special characters are allowed in the Label field:
    > `. _ - : / ( ) # , @ [ ] + = & ; { } ! $`

    ![](assets/control_panel_add_range2.png)

    >[!IMPORTANT]
    >
    >An IP range cannot overlap an existing range on the allow list. In that case, first delete the range that contains the overlapping IP.
    >
    >It is possible to add a range on the allow list for multiple instances. To do this, press the down arrow key or type the first letters of the desired instance, then select it from the suggestions list.

    ![](assets/control_panel_add_range3.png)

1. Click the **[!UICONTROL Save]** button. IP addition to the allow list will be displayed as PENDING until the request is fully processed. This should only take a few seconds.

To delete IP ranges from the allow list, select them then click the **[!UICONTROL Delete IP range]** button.

![](assets/control_panel_delete_range2.png)

>[!NOTE]
>
>It is currently not possible to edit a range on the allow list. To modify an IP range, delete it, then create a one corresponding to your needs.

## Monitoring changes {#monitoring-changes}

The **[!UICONTROL Job Logs]** in the Control Panel home page let you monitor all changes that have been made to IP addresses on the allow list.

For more on the Control Panel interface, refer to [this section](../../discover/using/discovering-the-interface.md).

![](assets/control_panel_ip_log.png)
