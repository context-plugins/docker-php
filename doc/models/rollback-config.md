
# Rollback Config

Specification for the rollback strategy of the service.

## Structure

`RollbackConfig`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `delay` | `?int` | Optional | Amount of time between rollback iterations, in nanoseconds. | getDelay(): ?int | setDelay(?int delay): void |
| `failureAction` | [`?string(FailureActionEnum)`](../../doc/models/failure-action-enum.md) | Optional | - | getFailureAction(): ?string | setFailureAction(?string failureAction): void |
| `maxFailureRatio` | `?float` | Optional | The fraction of tasks that may fail during a rollback before the failure action is invoked, specified as a floating point number between 0 and 1.<br><br>**Default**: `0` | getMaxFailureRatio(): ?float | setMaxFailureRatio(?float maxFailureRatio): void |
| `monitor` | `?int` | Optional | Amount of time to monitor each rolled back task for failures, in nanoseconds. | getMonitor(): ?int | setMonitor(?int monitor): void |
| `order` | [`?string(OrderEnum)`](../../doc/models/order-enum.md) | Optional | - | getOrder(): ?string | setOrder(?string order): void |
| `parallelism` | `?int` | Optional | Maximum number of tasks to be rolled back in one iteration (0 means unlimited parallelism). | getParallelism(): ?int | setParallelism(?int parallelism): void |

## Example

```php
use DockerLib\Models\Builders\RollbackConfigBuilder;
use DockerLib\Models\FailureActionEnum;
use DockerLib\Models\OrderEnum;

$rollbackConfig = RollbackConfigBuilder::init()
    ->delay(72)
    ->failureAction(FailureActionEnum::CONTINUE_)
    ->maxFailureRatio(0)
    ->monitor(50)
    ->order(OrderEnum::STOPFIRST)
    ->build();
```

