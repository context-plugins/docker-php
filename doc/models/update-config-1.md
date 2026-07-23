
# Update Config 1

## Structure

`UpdateConfig1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `delay` | `?int` | Optional | Amount of time between updates, in nanoseconds. | getDelay(): ?int | setDelay(?int delay): void |
| `failureAction` | [`?string(FailureAction1Enum)`](../../doc/models/failure-action-1-enum.md) | Optional | - | getFailureAction(): ?string | setFailureAction(?string failureAction): void |
| `maxFailureRatio` | `?float` | Optional | The fraction of tasks that may fail during an update before the failure action is invoked, specified as a floating point number between 0 and 1.<br><br>**Default**: `0` | getMaxFailureRatio(): ?float | setMaxFailureRatio(?float maxFailureRatio): void |
| `monitor` | `?int` | Optional | Amount of time to monitor each updated task for failures, in nanoseconds. | getMonitor(): ?int | setMonitor(?int monitor): void |
| `order` | [`?string(Order1Enum)`](../../doc/models/order-1-enum.md) | Optional | - | getOrder(): ?string | setOrder(?string order): void |
| `parallelism` | `?int` | Optional | Maximum number of tasks to be updated in one iteration (0 means unlimited parallelism). | getParallelism(): ?int | setParallelism(?int parallelism): void |

## Example

```php
use DockerLib\Models\Builders\UpdateConfig1Builder;
use DockerLib\Models\FailureAction1Enum;
use DockerLib\Models\Order1Enum;

$updateConfig1 = UpdateConfig1Builder::init()
    ->delay(204)
    ->failureAction(FailureAction1Enum::CONTINUE_)
    ->maxFailureRatio(0)
    ->monitor(82)
    ->order(Order1Enum::STOPFIRST)
    ->build();
```

