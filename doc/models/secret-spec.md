
# Secret Spec

## Structure

`SecretSpec`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `data` | `?string` | Optional | Base64-url-safe-encoded ([RFC 4648](https://tools.ietf.org/html/rfc4648#section-3.2))<br>data to store as secret.<br><br>This field is only used to _create_ a secret, and is not returned by<br>other endpoints. | getData(): ?string | setData(?string data): void |
| `driver` | [`?Driver1`](../../doc/models/driver-1.md) | Optional | - | getDriver(): ?Driver1 | setDriver(?Driver1 driver): void |
| `labels` | `?array<string,string>` | Optional | User-defined key/value metadata. | getLabels(): ?array | setLabels(?array labels): void |
| `name` | `?string` | Optional | User-defined name of the secret. | getName(): ?string | setName(?string name): void |

## Example

```php
use DockerLib\Models\Builders\SecretSpecBuilder;
use DockerLib\Models\Builders\Driver1Builder;

$secretSpec = SecretSpecBuilder::init()
    ->data('Data8')
    ->driver(
        Driver1Builder::init(
            'Name4'
        )
            ->options(
                [
                    'key0' => 'Options6'
                ]
            )
            ->build()
    )
    ->labels(
        [
            'com.example.some-label' => 'some-value',
            'com.example.some-other-label' => 'some-other-value'
        ]
    )
    ->name('Name4')
    ->build();
```

