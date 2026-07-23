
# Exec Json Response

## Structure

`ExecJsonResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `containerID` | `?string` | Optional | - | getContainerID(): ?string | setContainerID(?string containerID): void |
| `exitCode` | `?int` | Optional | - | getExitCode(): ?int | setExitCode(?int exitCode): void |
| `iD` | `?string` | Optional | - | getID(): ?string | setID(?string iD): void |
| `openStderr` | `?bool` | Optional | - | getOpenStderr(): ?bool | setOpenStderr(?bool openStderr): void |
| `openStdin` | `?bool` | Optional | - | getOpenStdin(): ?bool | setOpenStdin(?bool openStdin): void |
| `openStdout` | `?bool` | Optional | - | getOpenStdout(): ?bool | setOpenStdout(?bool openStdout): void |
| `pid` | `?int` | Optional | The system process ID for the exec process. | getPid(): ?int | setPid(?int pid): void |
| `processConfig` | [`?ProcessConfig`](../../doc/models/process-config.md) | Optional | - | getProcessConfig(): ?ProcessConfig | setProcessConfig(?ProcessConfig processConfig): void |
| `running` | `?bool` | Optional | - | getRunning(): ?bool | setRunning(?bool running): void |

## Example

```php
use DockerLib\Models\Builders\ExecJsonResponseBuilder;

$execJsonResponse = ExecJsonResponseBuilder::init()
    ->containerID('ContainerID2')
    ->exitCode(64)
    ->iD('ID8')
    ->openStderr(false)
    ->openStdin(false)
    ->build();
```

