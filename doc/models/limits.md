
# Limits

## Structure

`Limits`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `genericResources` | [`?(GenericResource[])`](../../doc/models/generic-resource.md) | Optional | User-defined resources can be either Integer resources (e.g, `SSD=3`) or String resources (e.g, `GPU=UUID1`) | getGenericResources(): ?array | setGenericResources(?array genericResources): void |
| `memoryBytes` | `?int` | Optional | - | getMemoryBytes(): ?int | setMemoryBytes(?int memoryBytes): void |
| `nanoCPUs` | `?int` | Optional | - | getNanoCPUs(): ?int | setNanoCPUs(?int nanoCPUs): void |

## Example

```php
use DockerLib\Models\Builders\LimitsBuilder;
use DockerLib\Models\Builders\GenericResourceBuilder;
use DockerLib\Models\Builders\DiscreteResourceSpecBuilder;
use DockerLib\Models\Builders\NamedResourceSpecBuilder;

$limits = LimitsBuilder::init()
    ->genericResources(
        [
            GenericResourceBuilder::init()
                ->discreteResourceSpec(
                    DiscreteResourceSpecBuilder::init()
                        ->kind('SSD')
                        ->value(3)
                        ->build()
                )
                ->namedResourceSpec(
                    NamedResourceSpecBuilder::init()
                        ->kind('Kind8')
                        ->value('Value8')
                        ->build()
                )
                ->build(),
            GenericResourceBuilder::init()
                ->discreteResourceSpec(
                    DiscreteResourceSpecBuilder::init()
                        ->kind('Kind8')
                        ->value(98)
                        ->build()
                )
                ->namedResourceSpec(
                    NamedResourceSpecBuilder::init()
                        ->kind('GPU')
                        ->value('UUID1')
                        ->build()
                )
                ->build(),
            GenericResourceBuilder::init()
                ->discreteResourceSpec(
                    DiscreteResourceSpecBuilder::init()
                        ->kind('Kind8')
                        ->value(98)
                        ->build()
                )
                ->namedResourceSpec(
                    NamedResourceSpecBuilder::init()
                        ->kind('GPU')
                        ->value('UUID2')
                        ->build()
                )
                ->build()
        ]
    )
    ->memoryBytes(8272408576)
    ->nanoCPUs(4000000000)
    ->build();
```

