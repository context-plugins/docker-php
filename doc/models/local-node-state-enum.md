
# Local Node State Enum

Current local status of this node.

## Enumeration

`LocalNodeStateEnum`

## Fields

| Name |
|  --- |
| `INACTIVE` |
| `PENDING` |
| `ACTIVE` |
| `ERROR` |
| `LOCKED` |

## Example

```php
use DockerLib\Models\LocalNodeStateEnum;

$localNodeState = LocalNodeStateEnum::ACTIVE;
```

