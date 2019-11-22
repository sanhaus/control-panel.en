---
title: Managing profiles
description: Learn more how to manage profiles with APIs.
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

# Managing profiles {#managing-profiles}

## Retrieving Profiles

>Sample GET request to retrieve all profiles.

```

-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'

```

>Response to the request.

```

{
    "content": [
        {
            "PKey": "<PKEY>",
            "age": 85,
            "birthDate": "1933-10-24",
            "blackList": false,
            "blackListAllLastModified": "",
            ...
        },
        ...,
        ...,
        ...
    ],
    "count": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile//_count?_lineStart=@sL3AJfHiOJZzn9Ytm0OSduPdEz_kYoaflOEfSS1N2-ttAfLl"
    },
    "next": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/?_lineStart=@sL3AJfHiOJZzn9Ytm0OSduPdEz_kYoaflOEfSS1N2-ttAfLl"
    },
    "serverSidePagination": true
}

```

Retrieving profiles is performed with a GET request.

You can add some filters, ordering and pagination.
To read more information on these parameters, consult the respective sections: [Filtering](#filtering), [Sorting](#sorting) and [Pagination](#pagination).

Fore more information on the **GET** request, refer to [this section](#get-post-patch-delete).
For more information on the **metadata** of the profile API, refer to [this section](#metadata-mechanism).

>[!NOTE]
>
>
Reminder : you must replace <code>&lt;ORGANIZATION&gt;</code> in the URL with your <b>personal organization ID</b>.


>Sample GET request to retrieve the first 10 email values.

```

-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'

```

>It returns the following values.

```

{
  "content": [
    "amy.dakota@mail.com",
    "kristen.smith@mail.com",
    "omalley@mail.com",
    "xander.harrys@mail.com",
    "jane.summer@mail.com",
    "gloria.boston@mail.com",
    "edward.snow@mail.com",
    "dorian.simons@mail.com",
    "peter.paolini@mail.com",
    "mingam+test08@adobe.com"
  ],
  "next": {
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10&_
    lineStart=@Qy2MRJCS67PFf8soTf4BzF7BXsq1Gbkp_e5lLj1TbE7HJKqc"
  }
}

```

>The "next" node returns the URL that gives you access to the 10 next email values.

## Updating Profiles

> Sample GET request to retrieve the profile with the "amy.dakota@mail.com" email address.

```

-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byEmail?email=amy.dakota@mail.com \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'

```

>Response to the request.

```

{
    "content": [
        {
            ...
            "domain": "mail.com",
            "email": "john.doe@mail.com",
            "emailFormat": "unknown",
            "externalId": "",
            "fax": "",
            "firstName": "",
            "gender": "unknown",
            "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/@2v1dr3ZKJveMDhAdh0MPnh9hNQQ93qb7AW6BNVVKknjwXvTZRBAgUqz1SNcB4ZndgjqOofx3BwBZYBftlmObISoM3rs",
            "isExternal": false,
            "lastModified": "2019-09-26 11:49:48.817Z",
            ...
        }
    ],
    "count": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile//byEmail/_count?email=john.doe@mail.com&_lineStart=@sL3AJfHiOJZzn9Ytm0OSduPdEz_kYoaflOEfSS1N2-ttAfLl",
        "value": 1
    },
    "serverSidePagination": true
}

```

>Sample PATCH request to update the "phone" attribute.

```

-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-d '{"phone":"3301020304"}'

```

>It returns the PKEY and URL to retrieve the updated profile.

```

{
    "PKey": "<PKEY>",
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/@2v1dr3ZKJveMDhAdh0MPnh9hNQQ93qb7AW6BNVVKknjwXvTZRBAgUqz1SNcB4ZndgjqOofx3BwBZYBftlmObISoM3rs"
}

```

In this example, we want to **update the phone field** in a profile with the email value "amy.dakota@mail.com".

1. The first step is to **retrieve the profile**. To accomplish this GET request, we use the **filter** "byEmail". To know more about filters and how to use them, refer to [this section](#filtering).

1. Then, in a second request, we will apply the **PATCH request** on the profile with the completed phone number in the payload.>[!NOTE]
>
>The Primary Key value of the profile must be integrated in the URL.

The PATCH pattern is `https://mc.adobe.io/<ORGANIZATION>/campaign/<apiName>/<resourceName>/<PKEY>`

<br/>To know more about PATCH requests, refer to [this section](#get-post-patch-delete).

To check if the PATCH request has updated the profile, we can perform a final GET request.

## Creating Profiles

>Sample POST request to create a profile with the email "john.doe@mail.com".

```

-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"email":"john.doe@mail.com"}'

```

>It returns the newly created profile, with the "john.doe@mail.com" email address.

```

{
    ...
    "created": "2019-09-26 11:49:48.817Z",
    "cryptedId": "u5e+EEGhALYQwgQJpsEIZy+NYz5KFCHy++ckfwZ+okq05UpQ6mWOP+U/KUh2slJFcwqarw==",
    "domain": "mail.com",
    "email": "john.doe@mail.com",
    "emailFormat": "unknown",
    "externalId": "",
    "fax": "",
    "firstName": "",
    "gender": "unknown",
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/>PKEY>",
    ...
}

```

This action can be done with a simple **POST request** on the **profile** resource.

>[!CAUTION]
>
>If you want to associate an <b>orgUnit</b> to the created profile, you need to extend the profile resource with this field and, after the publication of the extension, perform a POST request on the <b>profileAndServicesExt</b> endpoint.
For more on the profile's resource extension, refer to the <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">Campaign documentation</a>.
