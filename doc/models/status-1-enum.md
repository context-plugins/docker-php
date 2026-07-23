
# Status 1 Enum

The status of the container. For example, `"running"` or `"exited"`.

## Enumeration

`Status1Enum`

## Fields

| Name |
|  --- |
| `CREATED` |
| `RUNNING` |
| `PAUSED` |
| `RESTARTING` |
| `REMOVING` |
| `EXITED` |
| `DEAD` |

## Example

```php
use DockerLib\Models\Status1Enum;

$status1 = Status1Enum::PAUSED;
```

