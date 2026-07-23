
# Driver Config 2

## Structure

`DriverConfig2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | Name of the driver to use to create the volume. | getName(): ?string | setName(?string name): void |
| `options` | `?array<string,string>` | Optional | key/value map of driver specific options. | getOptions(): ?array | setOptions(?array options): void |

## Example

```php
use DockerLib\Models\Builders\DriverConfig2Builder;

$driverConfig2 = DriverConfig2Builder::init()
    ->name('Name6')
    ->options(
        [
            'key0' => 'Options8',
            'key1' => 'Options9',
            'key2' => 'Options0'
        ]
    )
    ->build();
```

