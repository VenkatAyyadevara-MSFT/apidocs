# List permissions

Retrieve a list of permission objects. The permissions collection includes potentially sensitive information and may not be available for every caller.

* For the owner of the item all permissions will be returned. This includes co-owners.
* For a non-owner caller only the permissions that apply to the caller are returned.
* Permission properties containing secrets (e.g. link.token and link.webUrl) are only returned for callers that are able to create the Permission:
  * For application permissions, that is only the app that matches the link.identity of the permission.
  * For other permissions, only first party applications will have access.

### Prerequisites
The following **scopes** are required to execute this API: 

  * Files.Read
 
### HTTP request
<!-- { "blockType": "ignored" } -->
```http
GET /drive/root/permissions
GET /drive/items/<id>/permissions
GET /drives/<id>/root/permissions
```
### Request headers
| Name       | Type | Description|
|:---------------|:--------|:----------|
| if-none-match  | string  | If this request header is included and the etag provided matches the current etag on the item, an `HTTP 304 Not Modified` response is returned.|

### Optional query parameters
|Name|Value|Description|
|:---------------|:--------|:-------|
|$count|none|The count of related entities can be requested by specifying the $count query option.|
|$expand|string|Comma-separated list of relationships to expand and include in the response. See relationships table of [permission](../resources/permission.md) for supported names. |
|$filter|string|Filter string that lets you filter the response based on a set of criteria.|
|$orderby|string|Comma-separated list of properties that are used to sort the order of items in the response collection.|
|$select|string|Comma-separated list of properties to include in the response.|
|$skip|int|The number of items to skip in a result set.|
|$skipToken|string|Paging token that is used to get the next set of results.|
|$top|int|The number of items to return in a result set.|


### Request body
Do not supply a request body for this method.
### Response
If successful, this method returns a `200 OK` response code and collection of [permission](../resources/permission.md) objects in the response body.

Effective permissions of an item can come from two sources: either permissions set directly on the item itself or that are inherited from the item's ancestors.

Callers can differentiate if the permission is inherited or not by checking the inheritedFrom property. This property is an itemReference resource referencing the ancestor that the permission is inherited from.

### Example
##### Request
Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "get_permissions"
}-->
```http
GET https://graph.microsoft.com/v1.0/drive/root/permissions
```
##### Response
Here is an example of the response.
<!-- {
  "blockType": "response",
  "truncated": false,
  "@odata.type": "microsoft.graph.permission",
  "isCollection": true
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 939

{
  "value": [
    {
      "grantedTo": {
        "application": {
          "displayName": "displayName-value",
          "id": "id-value"
        },
        "device": {
          "displayName": "displayName-value",
          "id": "id-value"
        },
        "user": {
          "displayName": "displayName-value",
          "id": "id-value"
        }
      },
      "id": "id-value",
      "invitation": {
        "email": "email-value",
        "redeemedBy": "redeemedBy-value",
        "signInRequired": true
      },
      "inheritedFrom": {
        "driveId": "driveId-value",
        "id": "id-value",
        "path": "path-value"
      },
      "link": {
        "application": {
          "displayName": "displayName-value",
          "id": "id-value"
        },
        "type": "type-value",
        "webUrl": "webUrl-value"
      },
      "roles": [
        "roles-value"
      ]
    }
  ]
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "List permissions",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->