# Update device

Update the properties of a device.
### Prerequisites
The following **scopes** are required to execute this API: 
### HTTP request
<!-- { "blockType": "ignored" } -->
```http
PATCH /devices/<objectId>
```
### Optional request headers
| Name       | Type | Description|
|:-----------|:------|:----------|
| X-Sample-Header  | string  | Sample HTTP header. Update accordingly or remove if not needed|

### Request body
In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|accountEnabled|Boolean| **true** if the account is enabled; otherwise, **false**. |
|alternativeSecurityIds|[AlternativeSecurityId](alternativesecurityid.md) collection| The **any** operator is required for filter expressions on multi-valued properties. Not nullable.           |
|approximateLastLogonTimestamp|DateTimeOffset|            The Timestamp type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 would look like this: `'2014-01-01T00:00:00Z'`|
|deviceId|Guid|            |
|deviceMetadata|String||
|deviceOSType|String|The type of operating system on the device.|
|deviceOSVersion|String|The version of the operating system on the device|
|deviceObjectVersion|Int32|            |
|devicePhysicalIds|String collection| Not nullable.            |
|deviceTrustType|String||
|displayName|String|The display name for the device.|
|isCompliant|Boolean|**true** if the device complies with Mobile Device Management (MDM) policies; otherwise, **false**.|
|isManaged|Boolean|**true** if the device is managed by a Mobile Device Management (MDM) app such as Intune; otherwise, **false**.|

### Response
If successful, this method returns a `200 OK` response code and updated [device](../resources/device.md) object in the response body.
### Example
##### Request
Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "update_device"
}-->
```http
PATCH https://graph.microsoft.com/v1.0/devices/<objectId>
Content-type: application/json
Content-length: 732

{
  "accountEnabled": true,
  "alternativeSecurityIds": [
    {
      "type": 99,
      "identityProvider": "identityProvider-value",
      "key": "key-value"
    }
  ],
  "approximateLastLogonTimestamp": "datetime-value",
  "deviceId": "deviceId-value",
  "deviceMetadata": "deviceMetadata-value",
  "deviceObjectVersion": 99,
  "deviceOSType": "deviceOSType-value",
  "deviceOSVersion": "deviceOSVersion-value",
  "devicePhysicalIds": [
    "devicePhysicalIds-value"
  ],
  "deviceTrustType": "deviceTrustType-value",
  "dirSyncEnabled": true,
  "displayName": "displayName-value",
  "lastDirSyncTime": "datetime-value",
  "objectType": "objectType-value",
  "objectId": "objectId-value",
  "deletionTimestamp": "datetime-value"
}
```
##### Response
Here is an example of the response.
<!-- {
  "blockType": "response",
  "truncated": false,
  "@odata.type": "microsoft.graph.device"
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 732

{
  "accountEnabled": true,
  "alternativeSecurityIds": [
    {
      "type": 99,
      "identityProvider": "identityProvider-value",
      "key": "key-value"
    }
  ],
  "approximateLastLogonTimestamp": "datetime-value",
  "deviceId": "deviceId-value",
  "deviceMetadata": "deviceMetadata-value",
  "deviceObjectVersion": 99,
  "deviceOSType": "deviceOSType-value",
  "deviceOSVersion": "deviceOSVersion-value",
  "devicePhysicalIds": [
    "devicePhysicalIds-value"
  ],
  "deviceTrustType": "deviceTrustType-value",
  "dirSyncEnabled": true,
  "displayName": "displayName-value",
  "lastDirSyncTime": "datetime-value",
  "objectType": "objectType-value",
  "objectId": "objectId-value",
  "deletionTimestamp": "datetime-value"
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Update device",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->