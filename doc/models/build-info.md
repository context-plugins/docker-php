
# Build Info

## Structure

`BuildInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `error` | `?string` | Optional | - | getError(): ?string | setError(?string error): void |
| `errorDetail` | [`?ErrorDetail`](../../doc/models/error-detail.md) | Optional | - | getErrorDetail(): ?ErrorDetail | setErrorDetail(?ErrorDetail errorDetail): void |
| `id` | `?string` | Optional | - | getId(): ?string | setId(?string id): void |
| `progress` | `?string` | Optional | - | getProgress(): ?string | setProgress(?string progress): void |
| `progressDetail` | [`?ProgressDetail`](../../doc/models/progress-detail.md) | Optional | - | getProgressDetail(): ?ProgressDetail | setProgressDetail(?ProgressDetail progressDetail): void |
| `status` | `?string` | Optional | - | getStatus(): ?string | setStatus(?string status): void |
| `stream` | `?string` | Optional | - | getStream(): ?string | setStream(?string stream): void |

## Example

```php
use DockerLib\Models\Builders\BuildInfoBuilder;
use DockerLib\Models\Builders\ErrorDetailBuilder;
use DockerLib\Models\Builders\ProgressDetailBuilder;

$buildInfo = BuildInfoBuilder::init()
    ->error('error8')
    ->errorDetail(
        ErrorDetailBuilder::init()
            ->code(118)
            ->message('message4')
            ->build()
    )
    ->id('id4')
    ->progress('progress8')
    ->progressDetail(
        ProgressDetailBuilder::init()
            ->code(114)
            ->message(224)
            ->build()
    )
    ->build();
```

