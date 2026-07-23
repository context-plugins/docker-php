
# Status

## Structure

`Status`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `containerStatus` | [`?ContainerStatus`](../../doc/models/container-status.md) | Optional | - | getContainerStatus(): ?ContainerStatus | setContainerStatus(?ContainerStatus containerStatus): void |
| `err` | `?string` | Optional | - | getErr(): ?string | setErr(?string err): void |
| `message` | `?string` | Optional | - | getMessage(): ?string | setMessage(?string message): void |
| `state` | [`?string(TaskStateEnum)`](../../doc/models/task-state-enum.md) | Optional | - | getState(): ?string | setState(?string state): void |
| `timestamp` | `?string` | Optional | - | getTimestamp(): ?string | setTimestamp(?string timestamp): void |

## Example

```php
use DockerLib\Models\Builders\StatusBuilder;
use DockerLib\Models\Builders\ContainerStatusBuilder;
use DockerLib\Models\TaskStateEnum;

$status = StatusBuilder::init()
    ->containerStatus(
        ContainerStatusBuilder::init()
            ->containerID('ContainerID0')
            ->exitCode(140)
            ->pID(126)
            ->build()
    )
    ->err('Err2')
    ->message('Message4')
    ->state(TaskStateEnum::COMPLETE)
    ->timestamp('Timestamp8')
    ->build();
```

