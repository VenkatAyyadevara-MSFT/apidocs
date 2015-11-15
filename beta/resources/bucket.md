# bucket resource type

The Bucket resource represents a bucket (or "custom column") for tasks in a plan in Office 365. It is contained in a [plan](plan.md) and can have a collection of [tasks](task.md).

### JSON representation

Here is a JSON representation of the resource

<!-- {
  "blockType": "resource",
  "optionalProperties": [
    "tasks"
  ],
  "@odata.type": "microsoft.graph.bucket"
}-->

```json
{
  "id": "String-value (identifier)",
  "name": "String-value",
  "orderHint": "String-value",
  "planId": "String-value",
  "tasks": [
    {
      "@odata.type": "microsoft.graph.task"
    }
  ]
}

```
### Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|String| Read-only. Id of the bucket.|
|name|String| Name of the bucket. |
|orderHint|String| Used to set the relative order of the buckets in the task board view. Consider three buckets in the order of: `'E'`, `'F'`, `'G'`. To make `'F'` the first bucket, set its `'orderHint'` to smaller than that of `'x'`. The comparison is an ordinal string comparison.|
|planId|String| Plan id to which the bucket belongs. |

### Relationships
| Relationship | Type	|Description|
|:---------------|:--------|:----------|
|tasks|[task](task.md) collection| Read-only. Nullable. Collection of tasks in the bucket. |

### Methods

| Method		   | Return Type	|Description|
|:---------------|:--------|:----------|
|[Get bucket](../api/bucket_get.md) | [bucket](bucket.md) |Read properties and relationships of bucket object.|
|[List tasks](../api/bucket_list_tasks.md) |[task](task.md) collection| Get a task object collection.|
|[Create bucket](../api/bucket_post_buckets.md) | None | Create a new bucket object. |
|[Update bucket](../api/bucket_update.md) | [bucket](bucket.md)	|Update bucket object. |
|[Delete bucket](../api/bucket_delete.md) | None |Delete bucket object. |

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "bucket resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->