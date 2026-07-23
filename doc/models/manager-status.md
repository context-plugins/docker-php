
# Manager Status

ManagerStatus represents the status of a manager.

It provides the current status of a node's manager component, if the node
is a manager.

## Structure

`ManagerStatus`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `addr` | `?string` | Optional | The IP address and port at which the manager is reachable. | getAddr(): ?string | setAddr(?string addr): void |
| `leader` | `?bool` | Optional | **Default**: `false` | getLeader(): ?bool | setLeader(?bool leader): void |
| `reachability` | [`?string(ReachabilityEnum)`](../../doc/models/reachability-enum.md) | Optional | - | getReachability(): ?string | setReachability(?string reachability): void |

## Example

```php
use DockerLib\Models\Builders\ManagerStatusBuilder;
use DockerLib\Models\ReachabilityEnum;

$managerStatus = ManagerStatusBuilder::init()
    ->addr('10.0.0.46:2377')
    ->leader(true)
    ->reachability(ReachabilityEnum::UNKNOWN)
    ->build();
```

