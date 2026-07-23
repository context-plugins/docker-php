
# Failure Action Enum

Action to take if an rolled back task fails to run, or stops running during the rollback.

## Enumeration

`FailureActionEnum`

## Fields

| Name |
|  --- |
| `CONTINUE_` |
| `PAUSE` |

## Example

```php
use DockerLib\Models\FailureActionEnum;

$failureAction = FailureActionEnum::CONTINUE_;
```

