
# Root FS

## Structure

`RootFS`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `baseLayer` | `?string` | Optional | - | getBaseLayer(): ?string | setBaseLayer(?string baseLayer): void |
| `layers` | `?(string[])` | Optional | - | getLayers(): ?array | setLayers(?array layers): void |
| `type` | `string` | Required | - | getType(): string | setType(string type): void |

## Example

```php
use DockerLib\Models\Builders\RootFSBuilder;

$rootFS = RootFSBuilder::init(
    'Type6'
)
    ->baseLayer('BaseLayer6')
    ->layers(
        [
            'Layers1',
            'Layers0',
            'Layers9'
        ]
    )
    ->build();
```

