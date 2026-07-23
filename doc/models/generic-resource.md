
# Generic Resource

## Structure

`GenericResource`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `discreteResourceSpec` | [`?DiscreteResourceSpec`](../../doc/models/discrete-resource-spec.md) | Optional | - | getDiscreteResourceSpec(): ?DiscreteResourceSpec | setDiscreteResourceSpec(?DiscreteResourceSpec discreteResourceSpec): void |
| `namedResourceSpec` | [`?NamedResourceSpec`](../../doc/models/named-resource-spec.md) | Optional | - | getNamedResourceSpec(): ?NamedResourceSpec | setNamedResourceSpec(?NamedResourceSpec namedResourceSpec): void |

## Example

```php
use DockerLib\Models\Builders\GenericResourceBuilder;
use DockerLib\Models\Builders\DiscreteResourceSpecBuilder;
use DockerLib\Models\Builders\NamedResourceSpecBuilder;

$genericResource = GenericResourceBuilder::init()
    ->discreteResourceSpec(
        DiscreteResourceSpecBuilder::init()
            ->kind('Kind8')
            ->value(98)
            ->build()
    )
    ->namedResourceSpec(
        NamedResourceSpecBuilder::init()
            ->kind('Kind8')
            ->value('Value8')
            ->build()
    )
    ->build();
```

