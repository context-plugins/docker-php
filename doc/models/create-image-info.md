
# Create Image Info

## Structure

`CreateImageInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `error` | `?string` | Optional | - | getError(): ?string | setError(?string error): void |
| `progress` | `?string` | Optional | - | getProgress(): ?string | setProgress(?string progress): void |
| `progressDetail` | [`?ProgressDetail`](../../doc/models/progress-detail.md) | Optional | - | getProgressDetail(): ?ProgressDetail | setProgressDetail(?ProgressDetail progressDetail): void |
| `status` | `?string` | Optional | - | getStatus(): ?string | setStatus(?string status): void |

## Example

```php
use DockerLib\Models\Builders\CreateImageInfoBuilder;
use DockerLib\Models\Builders\ProgressDetailBuilder;

$createImageInfo = CreateImageInfoBuilder::init()
    ->error('error8')
    ->progress('progress8')
    ->progressDetail(
        ProgressDetailBuilder::init()
            ->code(114)
            ->message(224)
            ->build()
    )
    ->status('status4')
    ->build();
```

