---
title: About subdomains
description: Learn more about subdomains
---

# About subdomain {#about-subdomains}

## Why setting up subdomains? {#why-setting-up-subdomains}

A subdomain is a division of your domain that can be used to isolate various types of traffic (corporate, marketing information, etc.).

Let's take the example of the "mybrand.com" domain, that is used to send both informative and marketing communications:

* info.mybrand.com for your internal communications
* marketing.mybrand.com for your prospecting emailings.

In this situation, you can decide to delegate the "marketing.mybrand.com" subdomain to Adobe Campaign. By doing this, you will help preserve the reputation of your domain and other subdomains. For example, if the "marketing.mybrand.com" subdomains ended up being blacklisted by Internet Service Providers due to bad deliverability, this would prevent the whole "mybrand.com" domain and "info.mybrand.com" subdomain from being blocked.

## Subdomain delegation methods {#subdomain-delegation-methods}

Subdomain delegation allows you to delegate a sub-section of your domain (technically a "DNS zone") for use with Adobe Campaign. Available setup methods are:

* **Full subdomain delegation to Adobe Campaign** (recommended)

    The subdomain is fully delegated to Adobe. Adobe is able to deliver the Campaign as a managed service by controlling and maintaining all aspects of DNS that are required for delivering, rendering and tracking of email campaigns.

* **Use of CNAMEs** (not recommended and not supported througg the Control Panel):

    Create a subdomain and use CNAMEs to point to Adobe-specific records. Using this setup, both Adobe and the customer share responsibility for maintaining DNS.

For more information on each of these methods (implied responsibility, requirements, etc.), refer to [this documentation](https://helpx.adobe.com/campaign/kb/domain-name-delegation.html).
