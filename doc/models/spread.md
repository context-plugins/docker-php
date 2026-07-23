
# Spread

## Structure

`Spread`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `spreadDescriptor` | `?string` | Optional | label descriptor, such as engine.labels.az | getSpreadDescriptor(): ?string | setSpreadDescriptor(?string spreadDescriptor): void |

## Example

```php
use DockerLib\Models\Builders\SpreadBuilder;

$spread = SpreadBuilder::init()
    ->spreadDescriptor('SpreadDescriptor2')
    ->build();
```

