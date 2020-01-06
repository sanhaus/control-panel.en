---
title: Renewing a subdomain's SSL certificate
description: Learn how to renew your subdomains' SSL certificates
---

# Renewing a subdomain's SSL certificate {#renewing-subdomains-ssl-certificates}

>[!NOTE]
>
>Subdomain delegation from the Control Panel is currently in beta, and subject to frequent updates and modifications without notification.

## About certificates renewal {#about-certificate-renewal-process}

The SSL certificate renewal process includes 3 steps:

1. **Generation of the Certificate Signing Request (CSR)**
    Adobe Customer Care generates a CSR for you. You will need to provide some information required to generate the CSR (such as Common Name, Organization Name and address, etc.).
1. **Purchase of the SSL certificate**
    Once the CSR is generated, you can download it and use it to purchase the SSL certificate from the Certificate Authority that your company approves.
1. **Installation of the SSL certificate**
    Once you purchase the SSL certificate, you can install it on the desired subdomain.

>[!NOTE]
>
>SSL certificates renewal through the Control Panel is available for **fully delegated subdomains** only.

## Generating a Certificate Signing Request (CSR) {#generating-csr}

To generate a Certificate Signing Request (CSR), follow these steps:

1. In the **[!UICONTROL Subdomains & Certificates]** card, select the desired instance, then click the **[!UICONTROL Manage Certificate]** button.

    ![](assets/renewal1.png)

1. Select **[!UICONTROL Generate a CSR]**, then click **[!UICONTROL Next]** to launch the wizard that will guide you through the CSR generation process.

    ![](assets/renewal2.png)

1. A form displays, with all the details required to generate your CSR.

    Make sure you fill in the requested information fully and accurately, otherwise the certificate may not be renewed (contact your internal team, Security and IT teams if necessary), then click **[!UICONTROL Next]**.

    * **[!UICONTROL Organization]**: official organization name.
    * **[!UICONTROL Organization Unit]**: unit linked to the subdomain (example: Marketing, IT).
    * **[!UICONTROL Instance]** (pre-filled): URL of the Campaign instance associated to the subdomain.

    ![](assets/renewal3.png)

1. Select the subdomains to include into the CSR, then click **[!UICONTROL OK]**.

    ![](assets/renewal4.png)

1. The selected subdomains display in the list. For each of them, select the subdomains to include, then click **[!UICONTROL Next]**.

    ![](assets/renewal5.png)

1. A summary of the subdomains to include in the CSR displays. Click **[!UICONTROL Submit]** to confirm your request.

    ![](assets/renewal6.png)

1. The .csr file corresponding to your selection is automatically generated and downloaded. You can now use it to purchase the SSL certificate from the Certificate Authority that your company approves.

## Purchasing a certificate with the CSR {#purchasing-certificate}

After obtaining a Certificate Signing Request CSR from the Control Panel, purchase an SSL certificate from a Certificate Authority approved by your organization.

## Installing the SSL certificate {#installing-ssl-certificate}

Once an SSL certificate has been purchased, you can install it on your instance. Before proceeding, make sure you are aware of the prerequisites below:

* The Certificate Signing Request (CSR) must have been generated from the Control Panel. Otherwise, you will not be able to install the certificate from the Control Panel.
* Make sure that the Certificate Signing Request (CSR) matches the subdomain that has been delegated to Adobe. For example, it cannot contain more subdomains that the one that has been delegated.
* The certificate must have a current date. It is not possible to install certificates with dates in the future.

To install the certificate, follow these steps:

1. In the **[!UICONTROL Subdomains & Certificates]** card, select the desired instance, then click the **[!UICONTROL Manage Certificate]** button.

    ![](assets/renewal1.png)

1. Click **[!UICONTROL Install SSL Certificate]**, then **[!UICONTROL Next]** to launch the wizard that will guide you through the certificate installation process.

    ![](assets/install1.png)

1. Select the .zip file that contains the certificate to install, then click **[!UICONTROL Submit]**.

    ![](assets/install2.png)

Once the SSL certificate is installed, the certificate's expiration date and status icon are updated accordingly.

Your subdomain's URL address will change from **http** to **https**.
