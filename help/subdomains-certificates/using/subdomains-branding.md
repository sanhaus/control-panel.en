---
title: Subdomains branding
description: Learn more about subdomains branding
---

# Subdomains branding {#subdomains-branding}

## Why setting up subdomains? {#why-setting-up-subdomains}

A subdomain is a division of your domain that can be used to isolate your brands, or various types of traffic (transactional messages, marketing information, etc.).

Let's take the example of the "mybrand.com" domain, that is used to send both transactional and marketing communications. In this situation, you can decide to set up two subdomains:

* "info.mybrand.com" subdomain for your transactional communications (purchases confirmation, password reset, etc.),
* "marketing.mybrand.com" subdomain for your prospecting emailings.

By doing so, you will help preserve the reputation of your domain and other subdomains. For example, if the "marketing.mybrand.com" subdomains ended up being blacklisted by Internet Service Providers due to bad deliverability, this would prevent the whole "mybrand.com" domain and the "info.mybrand.com" subdomain from being blacklisted.

## Subdomain delegation methods {#subdomain-delegation-methods}

Subdomain delegation allows you to delegate a sub-section of your domain (technically a "DNS zone") for use with Adobe Campaign. Available setup methods are:

* **Full subdomain delegation to Adobe Campaign** (recommended): The subdomain is fully delegated to Adobe. Adobe is able to deliver the Campaign as a managed service by controlling and maintaining all aspects of DNS that are required for delivering, rendering and tracking of email campaigns.

* **Use of CNAMEs** (not recommended and not supported through the Control Panel): Create a subdomain and use CNAMEs to point to Adobe-specific records. Using this setup, both Adobe and the customer share responsibility for maintaining DNS.

The table below provides a summary of how these methods work, as well as the implied level of effort:

 | Delegationmethod | How it works | Level of effort |
   |---|---|---|
   | **Full delegation** | Create the subdomain and namespace record. Adobe will then configure all DNS records required for Adobe Campaign. In this setup, Adobe is fully responsible for managing the sub-domain and all the DNS records. | Low |
   | **CNAME, custom method** |  Create the subdomain and namespace record. Adobe will then provide the records to be placed in your DNS servers and will configure the corresponding values in Adobe Campaign DNS servers. In this setup, both you and Adobe share responsibility for maintaining DNS. | High |

Additional information on domain delegation is available in[this documentation](https://helpx.adobe.com/campaign/kb/domain-name-delegation.html).
