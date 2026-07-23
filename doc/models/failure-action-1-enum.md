
# Failure Action 1 Enum

Action to take if an updated task fails to run, or stops running during the update.

## Enumeration

`FailureAction1Enum`

## Fields

| Name |
|  --- |
| `CONTINUE_` |
| `PAUSE` |
| `ROLLBACK` |

## Example

```php
use DockerLib\Models\FailureAction1Enum;

$failureAction1 = FailureAction1Enum::PAUSE;
```

