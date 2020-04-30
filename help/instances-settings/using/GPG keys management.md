---
title: GPG keys management
description: Learn how to manage GPG keys to encrypt and decrypt data within Campaign Classic.
---

# GPG keys management {#gpg-keys-management}

>[!IMPORTANT]
>
>This feature is available for Campaign Classic instances only.

## About GPG encryption {about-gpg-encryption}

GPG encryption allows you to protect your data using a system of public-private keys pairs. Once implemented, you can decrypt incoming data and encrypt your data before transfer occurs, to ensure that they will not be accessed by anyone without a valid matching key pair.

To implement GPG encryption with Campaign, GPG keys must be installed on a marketing instance by an Administrator user directly from the Control Panel.

You will then be able to:

* **Encrypt sent data**: Campaign Classic sends data out, and encrypts them with the installed public key.

* **Decrypt incoming data**: Campaign Classic receives data that has been encrypted from an outside system using a public key shared by the Control Panel. Campaign Classic decrypts the data using a private key that is generated from the Control Panel.

## Monitoring GPG keys

To access GPG keys installed and generated for your instances, open the **[!UICONTROL Instance settings]** card, then select the **[!UICONTROL GPG keys]** tab.

![](assets/gpg_list.png)

The list displays all encryption and decryption GPG keys that have been installed and generated for your instances with detailed information on each key:

* **[!UICONTROL Name]**: The name that has been defined when installing or generating the key.
* **[!UICONTROL Use case]**: This column specifies if the key has been installed for data encryption, or generated to allow data decrypt ion.
* **[!UICONTROL Fingerprint]**: the fingerprint of the key.
* **[!UICONTROL Expires]**: The key's expiration date. Note that Control Panel will notifies you 30 days, then 10 days before a key expires.

As a best practice, we recommend that you remove any key that you do not need anymore. To do this, click the **...** button then select **[!UICONTROL Delete Key].**.

![](assets/gpg_delete.png)

>[!IMPORTANT]
>
>Before removing a key, make sure that it is not used in any Campaign Classic workflow to prevent them from failing.

## Encrypting data {#encrypting-data}

Control Panel allows you to encrypt data coming out from your Campaign Classic instance.

To do this, you need to generate a GPG key pair from a PGP encryption tool, then install the public key into Control Panel. You will then be able to encrypt data before sending it from you instance. To do this, follow these steps:

1. Generate a GPG public/private key pair using a PGP encryption tool. Required parameters are:

    ```
    key_type="RSA",
    key_length=3072,
    name_real="Campaign Operations",
    name_comment=<User provided label>,
    name_email="CampaignOperations@adobe.com",
    expire_date="date" / "0" (no expiration date),
    passphrase="passphrase"
    ```

    >[!NOTE]
    >   
    >In order to identify the public key easily in Campaign workflows, include a comment in the key's UID field with the name of your choice.

1. Access the **[!UICONTROL GPG Keys]** tab, then select the instance on which you want to install the public key.

1. Click the **[!UICONTROL Install Key]** button.

    ![](assets/gpg_install_button.png)

1. Paste the public key that has been generated from your PGP encryption tool. You can also directly drag and drop the public key file.

    >[!NOTE]
    >
    >The public key should be in the OpenPGP format.

    ![](assets/gpg_install_paste.png)

2. Click the **!UICONTROL Install Key]** button.

Once the public key is installed, it displays in the list. You can use the **...** button to download it or copy its fingerpint.

![](assets/gpg_install_download.png)

The key is then available for use in Campaign Classic workflows. You can use it to encrypt data when using a **[!UICONTROL Data extraction (file)]** activity.

For more on this, refer to Campaign Classic documentation:

* [Zipping or encrypting a file](https://docs.adobe.com/content/help/en/campaign-classic/using/automating-with-workflows/general-operation/how-to-use-workflow-data.html#zipping-or-encrypting-a-file)
* [Data extraction (file) activity](https://docs.adobe.com/content/help/en/campaign-classic/using/automating-with-workflows/action-activities/extraction--file-.html)

## Decrypting data {#decrypting-data}

Control Panel allows you to decrypt external data coming into your Campaign Classic instances.

To do this, you need to generate a GPG key pair directly from the Control Panel.

* The **public key** will be shared with the external system, which will use it to encrypt the data to send to Campaign.
* The **private key** will be used by Campaign to decrypt the incoming encrypted data.

To generate a key pair in Control Panel, follow these steps:

1. Access the **[!UICONTROL GPG Keys]** tab, then select the desired Campaign Classic instance.

1. Click the **[!UICONTROL Generate Key]** button.

    ![](assets/gpg_generate.png)

1. Specify the name of the key, then click **!UICONTROL Generate Key]**. This name will help you identify the key to use for decryption in Campaign workflows

    ![](assets/gpg_generate_name.png)

Once the key pair is generated, the public key displays in the list. Note that decryption key pairs are generated with no expiration date.

You can use the **...** button to download the public key or copy its fingerpint.

![](assets/gpg_generate_list.png)

The pubic key is then available to be shared with any external system. Campaign Classic will be able to use the private key in **[!UICONTROL Data loading (file)]** activities to decrypt data that have been encrypted with the public key.

For more on this, refer to Campaign Classic documentation:

* [Unzipping or decrypting a file before processing](https://docs.adobe.com/content/help/en/campaign-classic/using/automating-with-workflows/general-operation/importing-data.html#unzipping-or-decrypting-a-file-before-processing)
* [Data loading (file) activity](https://docs.adobe.com/content/help/en/campaign-classic/using/automating-with-workflows/action-activities/data-loading--file-.html)