---
title: Control Panel releases
---

# Control Panel releases {#control-panel-releases}

Here you’ll find information about the latest Control Panel releases.

>[!NOTE]
>
>Please note that Control Panel is available for customers hosted on AWS only, except for hybrid environments which are not yet supported. No upgrades are required to access Control Panel. Please make sure you are an Admin user to access it.

## June 2020 {#june-2020}

**GPG keys management**

Install and/or generate GPG keys on a marketing instance, in order to encrypt data sent from Campaign and to decrypt incoming data. [Read more](instances-settings/using/gpg-keys-management.md)

**'Whitelist' / 'Blacklist' removal**

Both ‘whitelist’ and ‘blacklist’ terms have been removed from Adobe Campaign documentation. Some occurrences of these terms may still exist in the product UI, option names and internal code, but will be replaced in upcoming Campaign releases with ‘blocklist’ and ‘allowlist.’

**Active profiles monitoring**

Control Panel now allows you to monitor the number of active profiles that are used by your instances and counted for billing purposes. [Read more](performance-monitoring/using/active-profiles-monitoring.md)

>[!IMPORTANT]
>
>Active profiles monitoring from the Control Panel is available in beta, and subject to frequent updates and modifications without notice.
>
>The feature is available to customers hosted on AWS from Campaign Standard 10368 build and Campaign Classic 8931 build. If you are using a previous build, you need to upgrade to use this feature.

## May 2020 {#may-2020}

**GPG keys management**

Control Panel now allows you to generate a pair of GPG keys, so you can easily decrypt the data coming to Campaign from the outside. In addition, we have added a capability so you can install a public GPG key to encrypt data leaving Campaign. [Read more](instances-settings/using/gpg-keys-management.md)

**Certificate management for CNAME subdomains**

Control Panel now allows you to renew the SSL certificates of your subdomains that have been delegated with the CNAME method. [Read more](subdomains-certificates/using/renewing-subdomain-certificate.md)

## April 2020 {#april-2020}

**Google TXT record management**

Add Google TXT site verification record to all your subdomains used to send emails to Gmail addresses through the Campaign Control Panel. [Read more](subdomains-certificates/using/managing-txt-records.md)

**Database space monitoring**

Campaign Control Panel is equipped with database monitoring capabilities, allowing you to view your database space utilization on-demand and over time. [Read more](performance-monitoring/using/database-monitoring.md)

**Email alerting**

Campaign Control Panel is equipped with real-time email alerting capabilities, allowing you to login to the Control Panel and sign up to receive alerts when your system is at risk of performance deterioration, or an action is required to ensure high performance for the future. [Read more](performance-monitoring/using/email-alerting.md)

## January 2020 {#january-2020}

*January 22, 2020*

We’ve added new capabilities for Admin users to delegate subdomains and renew SSL certificates from Control Panel.

For more information, refer to these pages:
* [Setting up a new subdomain](subdomains-certificates/using/setting-up-new-subdomain.md)
* [Renewing a subdomain's SSL certificate](subdomains-certificates/using/renewing-subdomain-certificate.md)

>[!IMPORTANT]
>
>These features will be available in beta, and subject to frequent updates and modifications without notice.

## September 2019 {#september-2019}

*September 16, 2019*

We’ve added new capabilities for Admin users to add IP addresses to the allow list in order to connect to Campaign Classic instances.
Additionally, Admin users can now view the list of Campaign Classic instances and eligibility for build upgrades.

For more information, refer to the [dedicated documentation](instances-settings/using/ip-whitelisting-instance-access.md).

## August 2019 {#august-2019}

We’ve added new capabilities for Admin users to receive notifications before SSL certificates for their domains expire. For more information, refer to the [detailed documentation](subdomains-certificates/using/monitoring-ssl-certificates.md).

Additionally, Admin users can now delete SSH keys that were added to access SFTP servers.

## July 2019 {#july-2019}

We've added new features to empower Admin users to take greater control of Campaign Classic instance settings. New Control Panel capabilities include the ability to add URLs that Adobe Campaign connect to for data/file transfers.

For more information, refer to the [detailed documentation](instances-settings/using/url-permissions.md).
