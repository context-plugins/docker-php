
# Order 1 Enum

The order of operations when rolling out an updated task. Either the old task is shut down before the new task is started, or the new task is started before the old task is shut down.

## Enumeration

`Order1Enum`

## Fields

| Name |
|  --- |
| `STOPFIRST` |
| `STARTFIRST` |

## Example

```php
use DockerLib\Models\Order1Enum;

$order1 = Order1Enum::STOPFIRST;
```

