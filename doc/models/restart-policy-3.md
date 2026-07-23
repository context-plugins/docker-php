
# Restart Policy 3

## Structure

`RestartPolicy3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `maximumRetryCount` | `?int` | Optional | If `on-failure` is used, the number of times to retry before giving up | getMaximumRetryCount(): ?int | setMaximumRetryCount(?int maximumRetryCount): void |
| `name` | [`?string(NameEnum)`](../../doc/models/name-enum.md) | Optional | - | getName(): ?string | setName(?string name): void |

## Example

```php
use DockerLib\Models\Builders\RestartPolicy3Builder;
use DockerLib\Models\NameEnum;

$restartPolicy3 = RestartPolicy3Builder::init()
    ->maximumRetryCount(102)
    ->name(NameEnum::UNLESSSTOPPED)
    ->build();
```

