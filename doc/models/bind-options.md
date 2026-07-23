
# Bind Options

Optional configuration for the `bind` type.

## Structure

`BindOptions`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `propagation` | [`?string(PropagationEnum)`](../../doc/models/propagation-enum.md) | Optional | - | getPropagation(): ?string | setPropagation(?string propagation): void |

## Example

```php
use DockerLib\Models\Builders\BindOptionsBuilder;
use DockerLib\Models\PropagationEnum;

$bindOptions = BindOptionsBuilder::init()
    ->propagation(PropagationEnum::PRIVATE_)
    ->build();
```

