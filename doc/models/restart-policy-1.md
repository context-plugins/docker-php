
# Restart Policy 1

Specification for the restart policy which applies to containers created as part of this service.

## Structure

`RestartPolicy1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `condition` | [`?string(ConditionEnum)`](../../doc/models/condition-enum.md) | Optional | - | getCondition(): ?string | setCondition(?string condition): void |
| `delay` | `?int` | Optional | Delay between restart attempts. | getDelay(): ?int | setDelay(?int delay): void |
| `maxAttempts` | `?int` | Optional | Maximum attempts to restart a given container before giving up (default value is 0, which is ignored).<br><br>**Default**: `0` | getMaxAttempts(): ?int | setMaxAttempts(?int maxAttempts): void |
| `window` | `?int` | Optional | Windows is the time window used to evaluate the restart policy (default value is 0, which is unbounded).<br><br>**Default**: `0` | getWindow(): ?int | setWindow(?int window): void |

## Example

```php
use DockerLib\Models\Builders\RestartPolicy1Builder;
use DockerLib\Models\ConditionEnum;

$restartPolicy1 = RestartPolicy1Builder::init()
    ->condition(ConditionEnum::NONE)
    ->delay(78)
    ->maxAttempts(0)
    ->window(0)
    ->build();
```

