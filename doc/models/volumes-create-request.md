
# Volumes Create Request

## Structure

`VolumesCreateRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `driver` | `?string` | Optional | Name of the volume driver to use.<br><br>**Default**: `'local'` | getDriver(): ?string | setDriver(?string driver): void |
| `driverOpts` | `?array<string,string>` | Optional | A mapping of driver options and values. These options are passed directly to the driver and are driver specific. | getDriverOpts(): ?array | setDriverOpts(?array driverOpts): void |
| `labels` | `?array<string,string>` | Optional | User-defined key/value metadata. | getLabels(): ?array | setLabels(?array labels): void |
| `name` | `?string` | Optional | The new volume's name. If not specified, Docker generates a name. | getName(): ?string | setName(?string name): void |

## Example

```php
use DockerLib\Models\Builders\VolumesCreateRequestBuilder;

$volumesCreateRequest = VolumesCreateRequestBuilder::init()
    ->driver('custom')
    ->driverOpts(
        [
            'key0' => 'DriverOpts6',
            'key1' => 'DriverOpts7',
            'key2' => 'DriverOpts8'
        ]
    )
    ->labels(
        [
            'com.example.some-label' => 'some-value',
            'com.example.some-other-label' => 'some-other-value'
        ]
    )
    ->name('tardis')
    ->build();
```

