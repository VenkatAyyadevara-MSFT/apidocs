# directoryRole resource type

Represents an Azure AD directory role. Azure AD directory roles are also known as *administrator roles*. For more information about directory (administrator) roles, see [Assigning administrator roles in Azure AD](http://azure.microsoft.com/documentation/articles/active-directory-assign-admin-roles/). With the Microsoft Graph, you can assign users to directory roles to grant them the permissions of the target role. To read a directory role or update its members, it must first be activated in the tenant. Only the Company Administrators directory role is activated by default. To activate other available directory roles you send a POST request with the ID of the [directoryRoleTemplate](directoryroletemplate.md) on which the directory role is based. Inherits from [DirectoryObject](directoryobject.md). 

### JSON representation

Here is a JSON representation of the resource

<!-- {
  "blockType": "resource",
  "optionalProperties": [
    "memberOf",
    "members",
    "ownedObjects",
    "owners"
  ],
  "@odata.type": "microsoft.graph.directoryrole"
}-->

```json
{
  "deletionTimestamp": "String (timestamp)",
  "description": "String-value",
  "displayName": "String-value",
  "isSystem": true,
  "memberOf": [
    {
      "@odata.type": "microsoft.graph.directoryobject"
    }
  ],
  "members": [
    {
      "@odata.type": "microsoft.graph.directoryobject"
    }
  ],
  "objectId": "String-value (identifier)",
  "objectType": "String-value",
  "ownedObjects": [
    {
      "@odata.type": "microsoft.graph.directoryobject"
    }
  ],
  "owners": [
    {
      "@odata.type": "microsoft.graph.directoryobject"
    }
  ],
  "roleDisabled": true,
  "roleTemplateId": "String-value"
}

```
### Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|deletionTimestamp|DateTimeOffset|The Timestamp type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 would look like this: `'2014-01-01T00:00:00Z'`|
|description|String|The description for the directory role. Read-only. |
|displayName|String|The display name for the directory role. Read-only. |
|isSystem|Boolean| **true** if the role is a system role; otherwise, **false**. |
|objectId|String|The unique identifier for the directory role. Inherited from [DirectoryObject](directoryobject.md). Key, Not nullable, Read-only.|
|objectType|String|A string that identifies the object type. For directory roles the value is always “DirectoryRole”.  |
|roleDisabled|Boolean| **true** if the directory role is disabled; otherwise, **false**. |
|roleTemplateId|String| The **id** of the [DirectoryRoleTemplate](directoryroletemplate.md) that this role is based on. The property must be specified when activating a directory role in a tenant with a POST operation. After the directory role has been activated, the property is read only. |

### Relationships
| Relationship | Type	|Description|
|:---------------|:--------|:----------|
|members|[DirectoryObject](directoryobject.md) collection|Users that are members of this directory role. HTTP Methods: GET, POST, DELETE. Read-only. Nullable.|

### Methods

| Method		   | Return Type	|Description|
|:---------------|:--------|:----------|
|[Get directoryRole](../api/directoryrole_get.md) | [directoryRole](directoryrole.md) |Read properties and relationships of directoryRole object.|
|[Create member](../api/directoryrole_post_members.md) |[DirectoryObject](directoryobject.md)| Add a user to the directory role by posting to the members navigation property.|
|[List members](../api/directoryrole_list_members.md) |[DirectoryObject](directoryobject.md) collection| Get the users that are members of the directory role from the members navigation property.|

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "directoryRole resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->