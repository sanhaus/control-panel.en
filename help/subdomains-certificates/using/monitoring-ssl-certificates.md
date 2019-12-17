---
title: Monitoring subdomains' SSL certificates
description: Learn how to monitor your subdomains' SSL certificates
---

# Monitoring subdomains' SSL certificates {#monitoring-ssl-certificates}

Adobe Campaign recommends that you secure the subdomains that host your landing pages, especially those that are gathering sensitive information of your customers.

**SSL (Secure Socket Layer) encryption** ensures that the subdomains that you delegated to Adobe are secure. When your customer fills out a web form or visits a landing page hosted by Adobe Campaign, by default the information is sent over non-secure protocol (HTTP). To ensure additional security, secure sent information with a HTTPS protocol. For example, your "http://info.mywebsite.com/" subdomain address will now be "https://info.mywebsite.com/".

**SSL certificates are not installed on the delegated subdomains themselves**. They are installed on associated subdomains, mainly those that host landing pages, resource pages and others.

**SSL certificates are provided for a specific period of time** (1 year, 60 days, etc.). Once a certificate expires, you may experience issues when accessing the landing pages or using resources from the subdomain. To prevent this, the Control Panel allows you to monitor your subdomains' SSL certificates, as well as initiate their renewal process.

![](assets/no_certificate.png)

If one of your subdomain's SSL certificate is about to expire, you can renew it firectly from the Control Panel. For more on this, refer to this section: [Renewing a subdomain's SSL certificate](../../subdomains-certificates/using/renewing-subdomain-certificate).
