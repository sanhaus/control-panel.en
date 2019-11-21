---
title: Managing geographical units
description: Learn how to manage geographical units with APIs.
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

# Managing geographical units {#managing-geographical-units}

The **geoUnitBase** endpoint lets you interact with Geographical units, enabling you, for example, to update their attributes or update a profile's Geographcal unit.

<aside class="warning">The Geographical unit feature has been deprecated with the Campaign Standard 18.7 release.
As a result, new Campaign Standard instances, as well as existing instances with no geographical units created, cannot have this capability implemented starting the 18.7 release.
For more on this, refer to the <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">Deprecated features</a> page.</aside>

The <b>Geographcal unit</b> field is added to a profile when extending the profile resource. As a result, remember to always use the <b>profileAndServicesExt</b> endpoint to interact with Geographical units. For more on the profile's resource extension, refer to the [Campaign documentation](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles).

## Retrieving a profile's Geographical unit

>Retrieve the profile record.

```shell
$curl
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>It returns the geoUnit URL for the profile.

```shell
{
  ...
  "geoUnit": {
    "PKey": "@zYV4vIjP1wpBebml6s71hjGiDhs4_gHgbC_UhuJFk8h7XTZxZ5QnZrPnQPEfB__TxwR2ge6sz61D8RR4zvD75CLDZtc<PKEY>",
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY>",
    "title": "All (all)"
    },
  ...
}
```

>Perform a GET request on the URL to retrieve more information.

```shell
$curl
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>It returns the details below.

```shell
{
  "PKey": "<PKEY>",
  "created": "2019-04-02 22:36:13.252Z",
  "desc": "Default geographical entity (accessible to everyone)",
  "label": "All",
  "lastModified": "2019-04-03 08:17:19.100Z",
  "name": "all",
  "parentTitle": "",
  "title": "All (all)"
}
```

1. Perform a GET request on the profile PKey to retrieve the **geoUnit** URL.<br/><br/>
`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY>`

1. Perform a GET request on the URL to retrieve more details about the Geographical unit.<br/><br/>
`GET <GEO_UNIT_URL>`

## Updating a profile's Geographical unit

>Retrieve the list of Geographical units.

```shell
$curl
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>It returns all Geographical units. Retrieve the PKey of the unit to which you want to assign the profile.

```shell
{
 "PKey": "<PKEY>",
 "created": "2019-04-06 22:36:19.089Z",
 "desc": "",
 "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/<PKEY>",
 "label": "Europe",
 "lastModified": "2019-04-06 22:36:19.086Z",
 "name": "eu",
 "parentTitle": "All (all)",
 "title": "Europe (eu)"
},
```

>Perform a PATCH request on the profile, with the PKey of the desired Geographical unit in the payload.

```shell
$curl
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "geoUnit":{
-d    "PKey":"<PKEY>"
-d  }
-d }
```

<!-- + réponse -->

1. Perform a GET request on the **geoUnitBase** resource to retrieve the Geographical unit PKey.<br/><br/>
`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/`

1. Perform a PATCH request on the profile PKey, with the desired Geographical unit PKey in the payload.<br/><br/>
`PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY>`<br/>
`{`<br/>
`"geoUnit": {`<br/>
`       "PKey": "<PKEY>"`<br/>
`   }`<br/>
`}`

## Updating a Geographical unit attributes

>Retrieve the list of Geographical units.

```shell
$curl
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>It returns all Geographical units. Retrieve the PKey of the desired unit.

```shell
{
 "PKey": "<PKEY>",
 "created": "2019-04-06 22:36:19.089Z",
 "desc": "",
 "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/<PKEY>",
 "label": "Europe",
 "lastModified": "2019-04-06 22:36:19.086Z",
 "name": "eu",
 "parentTitle": "All (all)",
 "title": "Europe (eu)"
},
```

>Perform a PATCH request on the Geographical unit, with the attributes to update in the payload.

```shell
$curl
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "label":"Asia",
-d "name":"asia"
-d }
```

<!-- + réponse -->

1. Perform a GET request on the **geoUnitBase** resource to retrieve the Geographical unit PKey.<br/><br/>
`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/`

1. Perform a PATCH request on the Geographical unit, with the attributes to update in the payload.<br/><br/>
`PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/<PKEY>`<br/>
`{`<br/>
`"<ATTRIBUTE_NAME>":"<ATTRIBUTE_VALUE>"`<br/>
`}`
