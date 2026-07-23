
# Driver

Driver represents a driver (network, logging, secrets).

## Structure

`Driver`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `string` | Required | Name of the driver. | getName(): string | setName(string name): void |
| `options` | `?array<string,string>` | Optional | Key/value map of driver-specific options. | getOptions(): ?array | setOptions(?array options): void |

## Example

```php
use DockerLib\Models\Builders\DriverBuilder;

$driver = DriverBuilder::init(
    'some-driver'
)
    ->options(
        [
            'OptionA' => 'value for driver-specific option A',
            'OptionB' => 'value for driver-specific option B'
        ]
    )
    ->build();
```

