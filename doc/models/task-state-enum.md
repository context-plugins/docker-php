
# Task State Enum

## Enumeration

`TaskStateEnum`

## Fields

| Name |
|  --- |
| `NEW_` |
| `ALLOCATED` |
| `PENDING` |
| `ASSIGNED` |
| `ACCEPTED` |
| `PREPARING` |
| `READY` |
| `STARTING` |
| `RUNNING` |
| `COMPLETE` |
| `SHUTDOWN` |
| `FAILED` |
| `REJECTED` |

## Example

```php
use DockerLib\Models\TaskStateEnum;

$taskState = TaskStateEnum::ACCEPTED;
```

