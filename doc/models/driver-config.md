
# Driver Config

Map of driver specific options

## Structure

`DriverConfig`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | Name of the driver to use to create the volume. | getName(): ?string | setName(?string name): void |
| `options` | `?array<string,string>` | Optional | key/value map of driver specific options. | getOptions(): ?array | setOptions(?array options): void |

## Example

```php
use DockerLib\Models\Builders\DriverConfigBuilder;

$driverConfig = DriverConfigBuilder::init()
    ->name('Name8')
    ->options(
        [
            'key0' => 'Options0',
            'key1' => 'Options1'
        ]
    )
    ->build();
```

