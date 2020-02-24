---
title: Managing Google TXT records
description: Learn how to manage Google TXT records for domain ownership verification.
---

# Managing Google TXT records {#google-txt-records}

## About TXT records {#about-google-txt-records}

TXT records are a type of DNS records used to provide text information about a domain, that can be read by external sources.

In order to ensure high inbox rates, and low spam rates, some services like Google require that you add a TXT record to your domain setting in order to verify that you own the domain.

Currently, Gmail is among one of the most popular email addresses providers. In order to ensure good deliverability and successful delivery of emails to Gmail addresses, Adobe Campaign allows you to add special Googe site verification TXT records to your subdomains to ensure that it is verified.

## Adding a Google TXT record for a subdomain {#adding-a-google-txt-record}

To add a Google TXT record to your subdomain used to email Gmail addresses, follow these steps:

1. Navigate to the **[!UICONTROL Subdomain and Certificates]** card.
1. Select your instance, then click subdomain.
1. Domain details →  Add TXT record
1. enter information obtained from G Suite (these actions please look up on G Suite documentation) You can reference the product page of Google TXT, which is 1 level above this page for this information).  I generate the Google TXT record from G Suite Admin tools, and copy the value of the TXT record for the subdomain
1. Confirm addition of the record in the G Suite account. Until you confirm with Google site verification will not work. As an admin of Adobe Campaign, in order to finish the Google TXT record setup, I need to let Google know that the record was added to my subdomain. I navigate back to the G Suite and verify the Google TXT record with G Suite.

To delete a record, select it from the records list, then click Remove.

>[!NOTE]
>
>The only record that you can delete from the DNS records list if the record that you have previously added (in our case Google TXT).
