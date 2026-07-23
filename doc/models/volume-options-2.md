
# Volume Options 2

## Structure

`VolumeOptions2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `driverConfig` | [`?DriverConfig2`](../../doc/models/driver-config-2.md) | Optional | - | getDriverConfig(): ?DriverConfig2 | setDriverConfig(?DriverConfig2 driverConfig): void |
| `labels` | `?array<string,string>` | Optional | User-defined key/value metadata. | getLabels(): ?array | setLabels(?array labels): void |
| `noCopy` | `?bool` | Optional | Populate volume with data from the target.<br><br>**Default**: `false` | getNoCopy(): ?bool | setNoCopy(?bool noCopy): void |

## Example

```php
use DockerLib\Models\Builders\VolumeOptions2Builder;
use DockerLib\Models\Builders\DriverConfig2Builder;

$volumeOptions2 = VolumeOptions2Builder::init()
    ->driverConfig(
        DriverConfig2Builder::init()
            ->name('Name0')
            ->options(
                [
                    'key0' => 'Options2',
                    'key1' => 'Options3'
                ]
            )
            ->build()
    )
    ->labels(
        [
            'key0' => 'Labels8',
            'key1' => 'Labels7',
            'key2' => 'Labels6'
        ]
    )
    ->noCopy(false)
    ->build();
```

