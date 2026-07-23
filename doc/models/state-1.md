
# State 1

The state of the container.

## Structure

`State1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `dead` | `?bool` | Optional | - | getDead(): ?bool | setDead(?bool dead): void |
| `error` | `?string` | Optional | - | getError(): ?string | setError(?string error): void |
| `exitCode` | `?int` | Optional | The last exit code of this container | getExitCode(): ?int | setExitCode(?int exitCode): void |
| `finishedAt` | `?string` | Optional | The time when this container last exited. | getFinishedAt(): ?string | setFinishedAt(?string finishedAt): void |
| `oOMKilled` | `?bool` | Optional | Whether this container has been killed because it ran out of memory. | getOOMKilled(): ?bool | setOOMKilled(?bool oOMKilled): void |
| `paused` | `?bool` | Optional | Whether this container is paused. | getPaused(): ?bool | setPaused(?bool paused): void |
| `pid` | `?int` | Optional | The process ID of this container | getPid(): ?int | setPid(?int pid): void |
| `restarting` | `?bool` | Optional | Whether this container is restarting. | getRestarting(): ?bool | setRestarting(?bool restarting): void |
| `running` | `?bool` | Optional | Whether this container is running.<br><br>Note that a running container can be _paused_. The `Running` and `Paused`<br>booleans are not mutually exclusive:<br><br>When pausing a container (on Linux), the cgroups freezer is used to suspend<br>all processes in the container. Freezing the process requires the process to<br>be running. As a result, paused containers are both `Running` _and_ `Paused`.<br><br>Use the `Status` field instead to determine if a container's state is "running". | getRunning(): ?bool | setRunning(?bool running): void |
| `startedAt` | `?string` | Optional | The time when this container was last started. | getStartedAt(): ?string | setStartedAt(?string startedAt): void |
| `status` | [`?string(Status1Enum)`](../../doc/models/status-1-enum.md) | Optional | - | getStatus(): ?string | setStatus(?string status): void |

## Example

```php
use DockerLib\Models\Builders\State1Builder;

$state1 = State1Builder::init()
    ->dead(false)
    ->error('Error8')
    ->exitCode(86)
    ->finishedAt('FinishedAt8')
    ->oOMKilled(false)
    ->build();
```

