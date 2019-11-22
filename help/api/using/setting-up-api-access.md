---
title: Setting-up API access
description: Learn how to set up access to Campaign Standard APIs.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da

internal: n
snippet: y
---

# Setting up API access {#setting-up-api-access}

```

-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'

```

In all the code examples, you must replace variables with your personal identifiers. For more information on the API access configuration and how to retrieve these identifiers, refer to [this section](#setting-up-api-access).

>[!NOTE]
>
>One ORGANIZATION ID is provided for each of your instances :<br/><b>&lt;ORGANIZATION&gt;</b> : your production instance<br/><b>&lt;ORGANIZATION-mkt-stage1&gt;</b>: your stage instance<br/><brTo obtain your ORGANIZATION ID value, refer to your administrator or your Adobe technical contact. You can also retrieve it into Adobe I/O when creating a new integration, in the licenses list (see the <a href="https://www.adobe.io/authentication.html">Adobe IO documentation</a>).

Each request must contain the **&lt;ORGANIZATION&gt;** element. It is your personal ORGANIZATION ID and is provided by Adobe. This parameter has an URL syntax, for example:
`https://mc.adobe.io/myInstance.adobe.com/campaign/`

Each request must contain the parameters below:

* **&lt;ACCESS_TOKEN&gt;**: your personal access token, which must be used in each API request. To retrieve it, you must exchange your JSON Web Token for this access token through a POST request.

* **&lt;API_KEY&gt;**: your personal API Key. It is provided in Adobe I/O after creating a new integration to Adobe Campaign Service.

> ![alt text](/images/tenant.png)

<br/>

>[!CAUTION]
>
To manage certificates in Adobe IO, make sure you have <b>System administrator</b> rights on the organization or a <a href="https://helpx.adobe.com/enterprise/using/manage-developers.html">developer account</aIn the Admin console.

Adobe Campaign Standard API access is set up through the steps below. Each of these steps is detailed in the [Adobe IO documentation](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

1. **Check you have a digital certificate**, or create one if necessary. The public and private keys provided with the certificate are needed in the following steps.

1. **Create a new integration to Adobe Campaign Service** in Adobe IO and configure it. Your credentials will then be generated (API Key, Client secret...).

1. **Create a JSON Web Token (JWT)** from the credentials previously generated and sign it with your private key. The JWT encodes all of the identity and security information that is needed by Adobe to verify your identity and grant you access to the API.

1. **Exchange your JWT for an Access Token** through a POST request. This Access Token will have to be used in each header of your API requests.

>[!NOTE]
>
To establish a secure service-to-service Adobe I/O API session, you must create a JSON Web Token (JWT) that encapsulates the identity of your integration, and exchange it for an access token. Every request to an Adobe service must include the access token in the Authorization header, along with the API Key (Client ID) that was generated when you created the integration in the Adobe I/O Console.