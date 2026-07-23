
# Push Image Info

## Structure

`PushImageInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `error` | `?string` | Optional | - | getError(): ?string | setError(?string error): void |
| `progress` | `?string` | Optional | - | getProgress(): ?string | setProgress(?string progress): void |
| `progressDetail` | [`?ProgressDetail`](../../doc/models/progress-detail.md) | Optional | - | getProgressDetail(): ?ProgressDetail | setProgressDetail(?ProgressDetail progressDetail): void |
| `status` | `?string` | Optional | - | getStatus(): ?string | setStatus(?string status): void |

## Example

```php
use DockerLib\Models\Builders\PushImageInfoBuilder;
use DockerLib\Models\Builders\ProgressDetailBuilder;

$pushImageInfo = PushImageInfoBuilder::init()
    ->error('error6')
    ->progress('progress6')
    ->progressDetail(
        ProgressDetailBuilder::init()
            ->code(114)
            ->message(224)
            ->build()
    )
    ->status('status6')
    ->build();
```

