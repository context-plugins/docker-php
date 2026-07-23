
# Order Enum

The order of operations when rolling back a task. Either the old task is shut down before the new task is started, or the new task is started before the old task is shut down.

## Enumeration

`OrderEnum`

## Fields

| Name |
|  --- |
| `STOPFIRST` |
| `STARTFIRST` |

## Example

```php
use DockerLib\Models\OrderEnum;

$order = OrderEnum::STOPFIRST;
```

