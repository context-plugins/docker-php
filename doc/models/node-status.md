
# Node Status

NodeStatus represents the status of a node.

It provides the current status of the node, as seen by the manager.

## Structure

`NodeStatus`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `addr` | `?string` | Optional | IP address of the node. | getAddr(): ?string | setAddr(?string addr): void |
| `message` | `?string` | Optional | - | getMessage(): ?string | setMessage(?string message): void |
| `state` | [`?string(NodeStateEnum)`](../../doc/models/node-state-enum.md) | Optional | - | getState(): ?string | setState(?string state): void |

## Example

```php
use DockerLib\Models\Builders\NodeStatusBuilder;
use DockerLib\Models\NodeStateEnum;

$nodeStatus = NodeStatusBuilder::init()
    ->addr('172.17.0.2')
    ->message('Message8')
    ->state(NodeStateEnum::UNKNOWN)
    ->build();
```

