
# Dispatcher

Dispatcher configuration.

## Structure

`Dispatcher`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `heartbeatPeriod` | `?int` | Optional | The delay for an agent to send a heartbeat to the dispatcher. | getHeartbeatPeriod(): ?int | setHeartbeatPeriod(?int heartbeatPeriod): void |

## Example

```php
use DockerLib\Models\Builders\DispatcherBuilder;

$dispatcher = DispatcherBuilder::init()
    ->heartbeatPeriod(5000000000)
    ->build();
```

