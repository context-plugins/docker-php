
# Blkio Weight Device

## Structure

`BlkioWeightDevice`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `path` | `?string` | Optional | - | getPath(): ?string | setPath(?string path): void |
| `weight` | `?int` | Optional | **Constraints**: `>= 0` | getWeight(): ?int | setWeight(?int weight): void |

## Example

```php
use DockerLib\Models\Builders\BlkioWeightDeviceBuilder;

$blkioWeightDevice = BlkioWeightDeviceBuilder::init()
    ->path('Path0')
    ->weight(86)
    ->build();
```

