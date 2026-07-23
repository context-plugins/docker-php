
# Log Driver 3

## Structure

`LogDriver3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | The log driver to use as a default for new tasks. | getName(): ?string | setName(?string name): void |
| `options` | `?array<string,string>` | Optional | Driver-specific options for the selectd log driver, specified<br>as key/value pairs. | getOptions(): ?array | setOptions(?array options): void |

## Example

```php
use DockerLib\Models\Builders\LogDriver3Builder;

$logDriver3 = LogDriver3Builder::init()
    ->name('json-file')
    ->options(
        [
            'max-file' => '10',
            'max-size' => '100m'
        ]
    )
    ->build();
```

