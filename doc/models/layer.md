
# Layer

## Structure

`Layer`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `digest` | `?string` | Optional | image layer digest | getDigest(): ?string | setDigest(?string digest): void |
| `instruction` | `?string` | Optional | Dockerfile instruction | getInstruction(): ?string | setInstruction(?string instruction): void |
| `size` | `?int` | Optional | size of the layer | getSize(): ?int | setSize(?int size): void |

## Example

```php
use DockerLib\Models\Builders\LayerBuilder;

$layer = LayerBuilder::init()
    ->digest('digest0')
    ->instruction('instruction4')
    ->size(216)
    ->build();
```

