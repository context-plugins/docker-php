
# Status 4

## Structure

`Status4`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `addr` | `?string` | Optional | IP address of the node. | getAddr(): ?string | setAddr(?string addr): void |
| `message` | `?string` | Optional | - | getMessage(): ?string | setMessage(?string message): void |
| `state` | [`?string(NodeStateEnum)`](../../doc/models/node-state-enum.md) | Optional | - | getState(): ?string | setState(?string state): void |

## Example

```php
use DockerLib\Models\Builders\Status4Builder;
use DockerLib\Models\NodeStateEnum;

$status4 = Status4Builder::init()
    ->addr('172.17.0.2')
    ->message('Message8')
    ->state(NodeStateEnum::READY)
    ->build();
```

