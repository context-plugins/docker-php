
# Node Spec

## Structure

`NodeSpec`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `availability` | [`?string(AvailabilityEnum)`](../../doc/models/availability-enum.md) | Optional | - | getAvailability(): ?string | setAvailability(?string availability): void |
| `labels` | `?array<string,string>` | Optional | User-defined key/value metadata. | getLabels(): ?array | setLabels(?array labels): void |
| `name` | `?string` | Optional | Name for the node. | getName(): ?string | setName(?string name): void |
| `role` | [`?string(RoleEnum)`](../../doc/models/role-enum.md) | Optional | - | getRole(): ?string | setRole(?string role): void |

## Example

```php
use DockerLib\Models\Builders\NodeSpecBuilder;
use DockerLib\Models\AvailabilityEnum;
use DockerLib\Models\RoleEnum;

$nodeSpec = NodeSpecBuilder::init()
    ->availability(AvailabilityEnum::ACTIVE)
    ->labels(
        [
            'foo' => 'bar'
        ]
    )
    ->name('node-name')
    ->role(RoleEnum::MANAGER)
    ->build();
```

