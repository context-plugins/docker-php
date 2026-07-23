
# Bind Options 2

## Structure

`BindOptions2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `propagation` | [`?string(PropagationEnum)`](../../doc/models/propagation-enum.md) | Optional | - | getPropagation(): ?string | setPropagation(?string propagation): void |

## Example

```php
use DockerLib\Models\Builders\BindOptions2Builder;
use DockerLib\Models\PropagationEnum;

$bindOptions2 = BindOptions2Builder::init()
    ->propagation(PropagationEnum::PRIVATE_)
    ->build();
```

