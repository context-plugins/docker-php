
# Log Driver 12

## Structure

`LogDriver12`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | - | getName(): ?string | setName(?string name): void |
| `options` | `?array<string,string>` | Optional | - | getOptions(): ?array | setOptions(?array options): void |

## Example

```php
use DockerLib\Models\Builders\LogDriver12Builder;

$logDriver12 = LogDriver12Builder::init()
    ->name('Name8')
    ->options(
        [
            'key0' => 'Options0',
            'key1' => 'Options9',
            'key2' => 'Options8'
        ]
    )
    ->build();
```

