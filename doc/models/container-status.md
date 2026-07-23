
# Container Status

## Structure

`ContainerStatus`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `containerID` | `?string` | Optional | - | getContainerID(): ?string | setContainerID(?string containerID): void |
| `exitCode` | `?int` | Optional | - | getExitCode(): ?int | setExitCode(?int exitCode): void |
| `pID` | `?int` | Optional | - | getPID(): ?int | setPID(?int pID): void |

## Example

```php
use DockerLib\Models\Builders\ContainerStatusBuilder;

$containerStatus = ContainerStatusBuilder::init()
    ->containerID('ContainerID2')
    ->exitCode(102)
    ->pID(88)
    ->build();
```

