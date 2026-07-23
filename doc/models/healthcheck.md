
# Healthcheck

## Structure

`Healthcheck`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `interval` | `?int` | Optional | The time to wait between checks in nanoseconds. It should be 0 or at least 1000000 (1 ms). 0 means inherit. | getInterval(): ?int | setInterval(?int interval): void |
| `retries` | `?int` | Optional | The number of consecutive failures needed to consider a container as unhealthy. 0 means inherit. | getRetries(): ?int | setRetries(?int retries): void |
| `startPeriod` | `?int` | Optional | Start period for the container to initialize before starting health-retries countdown in nanoseconds. It should be 0 or at least 1000000 (1 ms). 0 means inherit. | getStartPeriod(): ?int | setStartPeriod(?int startPeriod): void |
| `test` | `?(string[])` | Optional | The test to perform. Possible values are:<br><br>- `[]` inherit healthcheck from image or parent image<br>- `["NONE"]` disable healthcheck<br>- `["CMD", args...]` exec arguments directly<br>- `["CMD-SHELL", command]` run command with system's default shell | getTest(): ?array | setTest(?array test): void |
| `timeout` | `?int` | Optional | The time to wait before considering the check to have hung. It should be 0 or at least 1000000 (1 ms). 0 means inherit. | getTimeout(): ?int | setTimeout(?int timeout): void |

## Example

```php
use DockerLib\Models\Builders\HealthcheckBuilder;

$healthcheck = HealthcheckBuilder::init()
    ->interval(52)
    ->retries(204)
    ->startPeriod(124)
    ->test(
        [
            'Test8'
        ]
    )
    ->timeout(34)
    ->build();
```

