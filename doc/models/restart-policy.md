
# Restart Policy

The behavior to apply when the container exits. The default is not to restart.

An ever increasing delay (double the previous delay, starting at 100ms) is added before each restart to prevent flooding the server.

## Structure

`RestartPolicy`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `maximumRetryCount` | `?int` | Optional | If `on-failure` is used, the number of times to retry before giving up | getMaximumRetryCount(): ?int | setMaximumRetryCount(?int maximumRetryCount): void |
| `name` | [`?string(NameEnum)`](../../doc/models/name-enum.md) | Optional | - | getName(): ?string | setName(?string name): void |

## Example

```php
use DockerLib\Models\Builders\RestartPolicyBuilder;
use DockerLib\Models\NameEnum;

$restartPolicy = RestartPolicyBuilder::init()
    ->maximumRetryCount(118)
    ->name(NameEnum::ONFAILURE)
    ->build();
```

