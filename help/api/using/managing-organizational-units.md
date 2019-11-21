---
title: Managing organizational units
description: Learn how to manage organizational units with APIs.
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

# Managing organizational units {#managing-organizational-units}

The **orgUnitBase** endpoint lets you interact with Organizational units, enabling you, for example, to update their attributes or update a profile's Organizational unit.
For more on Organizational units in Campaign, refer to the [Campaign documentation](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html).

The <b>Organizational unit</b> field is added to a profile when extending the profile resource. As a result, remember to always use the <b>profileAndServicesExt</b> endpoint to interact with Geographical units. For more on the profile's resource extension, refer to the [Campaign documentation](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles).

## Retrieving a profile's Organization unit

>Retrieve the profile record.

```shell
$curl
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>It returns the orgUnit URL for the profile.

```shell
{
  ...
  "orgUnit": {
    "PKey": "<PKEY>",
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY>",
    "title": "All (all)"
    },
  ...
}
```

>Perform a GET request on the URL to retrieve more information.

```shell
$curl
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY> \
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
  "desc": "",
  "label": "Brand 4",
  "lastModified": "2019-04-03 08:17:19.100Z",
  "name": "brand4",
  "parentTitle": "All (all)",
  "title": "Brand 4 (brand4)"
}
```

1. Perform a GET request on the profile PKey to retrieve the **orgUnit** URL.<br/><br/>
`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY>`

1. Perform a GET request on the URL to retrieve more details about the Organizational unit.<br/><br/>
`GET <ORG_UNIT_URL>`

## Updating a profile's Organizational unit

>Retrieve the list of Organizational units.

```shell
$curl
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>It returns all Organizational units. Retrieve the PKey of the unit to which you want to assign the profile.

```shell
{
  "PKey": "<PKEY>",
  "created": "2019-04-02 22:36:13.252Z",
  "desc": "",
  "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY>",
  "label": "Brand 4",
  "lastModified": "2019-04-03 07:34:56.579Z",
  "name": "brand4",
  "parentTitle": "All (all)",
  "title": "Brand 4 (brand1)"
},
```

>Perform a PATCH request on the profile, with the PKey of the desired Organizational unit in the payload.

```shell
$curl
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "orgUnit":{
-d    "PKey":"<PKEY>"
-d  }
-d }
```

<!-- + réponse -->

1. Perform a GET request on the **orgUnitBase** resource to retrieve the Organizational unit PKey.<br/><br/>
`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/`

1. Perform a PATCH request on the profile PKey, with the desired Organizational unit PKey in the payload.<br/><br/>
`PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY>`<br/>
`{`<br/>
`"orgUnit": {`<br/>
`       "PKey": "<PKEY>"`<br/>
`   }`<br/>
`}`

## Updating an Organizational unit attributes

>Retrieve the list of Organizational units.

```shell
$curl
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>It returns all Organizational units. Retrieve the PKey of the desired unit.

```shell
{
  "PKey": "<PKEY>",
  "created": "2019-04-02 22:36:13.252Z",
  "desc": "",
  "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY>",
  "label": "Brand 4",
  "lastModified": "2019-04-03 07:34:56.579Z",
  "name": "brand4",
  "parentTitle": "All (all)",
  "title": "Brand 4 (brand1)"
},
```

>Perform a PATCH request on the Organizational unit, with the attributes to update in the payload.

```shell
$curl
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "label":"brand1",
-d "name":"brand1"
-d }
```

<!-- + réponse -->

1. Perform a GET request on the **orgUnitBase** resource to retrieve the Organizational unit PKey.<br/><br/>
`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/`

1. Perform a PATCH request on the Organizational unit, with the attributes to update in the payload.<br/><br/>
`PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY>`<br/>
`{`<br/>
`"<ATTRIBUTE_NAME>":"<ATTRIBUTE_VALUE>"`<br/>
`}`
