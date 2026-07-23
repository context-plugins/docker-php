
# Config Spec

## Structure

`ConfigSpec`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `data` | `?string` | Optional | Base64-url-safe-encoded ([RFC 4648](https://tools.ietf.org/html/rfc4648#section-3.2))<br>config data. | getData(): ?string | setData(?string data): void |
| `labels` | `?array<string,string>` | Optional | User-defined key/value metadata. | getLabels(): ?array | setLabels(?array labels): void |
| `name` | `?string` | Optional | User-defined name of the config. | getName(): ?string | setName(?string name): void |

## Example

```php
use DockerLib\Models\Builders\ConfigSpecBuilder;

$configSpec = ConfigSpecBuilder::init()
    ->data('Data0')
    ->labels(
        [
            'key0' => 'Labels6'
        ]
    )
    ->name('Name6')
    ->build();
```

