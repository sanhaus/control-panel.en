---
title: Setting up a new subdomain
description: Learn how to set up a new subdomain for your campaign instances
---

# Setting up a new subdomain {#setting-up-new-subdomain}

intro

>[!NOTE]
>
>Subdomain delegation from the Control Panel is currently in beta.

To set up a new subdomain to delegate to Adobe, follow these steps:

1. In the **[!UICONTROL Subdomains & Certificates]** card, select the desired instance, then click the **[!UICONTROL Setup new subdomain]** button.

    ![](assets/subdomain1.png)

1. Select the method you want to use for subdomain delegation, then cick **[!UICONTROL Next]**.

    Note that, currently, **Delegation to Adobe** is the only supported method.

    ![](assets/subdomain3.png)

1. Create the desired subdomain in the hosting solution used by your organization. To do this, copy the Adobe Nameserver information displayed in the wizard, then paste it into your hosting solution.

    For more on how to create a subdomain in a hosting solution, refer to the tutorial video available in the wizard.

    ![](assets/subdomain4.png)

    Once the subdomain is created with the corresponding Adobe nameserver information, click **[!UICONTROL Next]**.

1. Select the desired use case for the subdomain, then click **[!UICONTROL Next]**. Available use cases are **Marketing communications** or **Transactional & operational communications**.

    >[!NOTE]
    >
    >You can only select a use case that has been configured for your instance. If the instance has been configured for "Marketing communications" only, you will not be able to select the "Transactional & operaiton communications" use case.

    ![](assets/subdomain5.png)

1. Enter the subdomain that you created into your hosting solution with the Adobe Nameserver information, then click **[Submit]**.

    ![](assets/subdomain6.png)

1. Once the subdomain is submitted, the Control Panel will configure it and validate that it correctly points to Adobe Campaign.

    For more details on the various checks that are performed, click the **[!UICONTROL Process details]** button.

    ![](assets/subdomain7.png)
