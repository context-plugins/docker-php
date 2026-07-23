
# Discrete Resource Spec

## Structure

`DiscreteResourceSpec`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `kind` | `?string` | Optional | - | getKind(): ?string | setKind(?string kind): void |
| `value` | `?int` | Optional | - | getValue(): ?int | setValue(?int value): void |

## Example

```php
use DockerLib\Models\Builders\DiscreteResourceSpecBuilder;

$discreteResourceSpec = DiscreteResourceSpecBuilder::init()
    ->kind('Kind6')
    ->value(218)
    ->build();
```

