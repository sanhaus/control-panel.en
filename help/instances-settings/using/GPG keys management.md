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

## Monitoring your GPG keys

To access GPG keys installed and generated for your instances, open the **[!UICONTROL Instance settings]** card, then select the **[!UICONTROL GPG keys]** tab.

The list displays all encryption and decryption GPG keys that have been installed and generated for your instances with detailed information on each key:

* **[!UICONTROL Name]**: The name that has been defined when installing or generating the key.
* **[!UICONTROL Use case]**: this column specifies if the key has been installed for data encryption, or generated to allow data decryption.
* **[!UICONTROL Fingerprint]**: the fingerprint of the key.
* **[!UICONTROL Expires]**: The key's expiration date. Note that Control Panel will notifies you 30 days, then 10 days before a key expires.

AS a best practice, we recommend that you remove any key that you do not need anymore. To do this, click the button then select click Delete. 

>[!IMPORTANT]
>
>Before removing a key, make sure that it is not used in any Campaign Classic workflow to prevent them from failing.

## Encrypting data

importing public key so that they can encrypt data with the key before sending it
- generate a GPG key using pgp utility
 - install the public key in control panel

install: (to encrypt data)
to install a public key on an instance:
     - click install key button
            - type name : name will help identify the key, when using is in campaign workflow
            - paste the public key: can drag it, paste it
            - click intstall key
            - confirmation key has been installed
when issue installing a key, warning displays. … button / reinstall key to retry
once installed, key becomes available for use in extract file workflow activity. It is identified by the label of the key enteed in control panel

- use key in extract file activity

## Decrypting data

- generate a GPG key through the control panel

generate: (to decrypt data)
            - click generate key button
            - type name
            - expiraty date (or never expire)
            - generate key
            - once key generated, green pop-up : Download Key OR click … button / download

- use the key in load file activity
