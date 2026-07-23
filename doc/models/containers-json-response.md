
# Containers Json Response

## Structure

`ContainersJsonResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `appArmorProfile` | `?string` | Optional | - | getAppArmorProfile(): ?string | setAppArmorProfile(?string appArmorProfile): void |
| `args` | `?(string[])` | Optional | The arguments to the command being run | getArgs(): ?array | setArgs(?array args): void |
| `config` | [`?Config3`](../../doc/models/config-3.md) | Optional | - | getConfig(): ?Config3 | setConfig(?Config3 config): void |
| `created` | `?string` | Optional | The time the container was created | getCreated(): ?string | setCreated(?string created): void |
| `driver` | `?string` | Optional | - | getDriver(): ?string | setDriver(?string driver): void |
| `execIDs` | `?string` | Optional | - | getExecIDs(): ?string | setExecIDs(?string execIDs): void |
| `graphDriver` | [`?GraphDriver`](../../doc/models/graph-driver.md) | Optional | - | getGraphDriver(): ?GraphDriver | setGraphDriver(?GraphDriver graphDriver): void |
| `hostConfig` | [`?HostConfig1`](../../doc/models/host-config-1.md) | Optional | - | getHostConfig(): ?HostConfig1 | setHostConfig(?HostConfig1 hostConfig): void |
| `hostnamePath` | `?string` | Optional | - | getHostnamePath(): ?string | setHostnamePath(?string hostnamePath): void |
| `hostsPath` | `?string` | Optional | - | getHostsPath(): ?string | setHostsPath(?string hostsPath): void |
| `id` | `?string` | Optional | The ID of the container | getId(): ?string | setId(?string id): void |
| `image` | `?string` | Optional | The container's image | getImage(): ?string | setImage(?string image): void |
| `logPath` | `?string` | Optional | - | getLogPath(): ?string | setLogPath(?string logPath): void |
| `mountLabel` | `?string` | Optional | - | getMountLabel(): ?string | setMountLabel(?string mountLabel): void |
| `mounts` | [`?(MountPoint[])`](../../doc/models/mount-point.md) | Optional | - | getMounts(): ?array | setMounts(?array mounts): void |
| `name` | `?string` | Optional | - | getName(): ?string | setName(?string name): void |
| `networkSettings` | [`?NetworkSettings1`](../../doc/models/network-settings-1.md) | Optional | - | getNetworkSettings(): ?NetworkSettings1 | setNetworkSettings(?NetworkSettings1 networkSettings): void |
| `node` | `?array` | Optional | TODO | getNode(): ?array | setNode(?array node): void |
| `path` | `?string` | Optional | The path to the command being run | getPath(): ?string | setPath(?string path): void |
| `processLabel` | `?string` | Optional | - | getProcessLabel(): ?string | setProcessLabel(?string processLabel): void |
| `resolvConfPath` | `?string` | Optional | - | getResolvConfPath(): ?string | setResolvConfPath(?string resolvConfPath): void |
| `restartCount` | `?int` | Optional | - | getRestartCount(): ?int | setRestartCount(?int restartCount): void |
| `sizeRootFs` | `?int` | Optional | The total size of all the files in this container. | getSizeRootFs(): ?int | setSizeRootFs(?int sizeRootFs): void |
| `sizeRw` | `?int` | Optional | The size of files that have been created or changed by this container. | getSizeRw(): ?int | setSizeRw(?int sizeRw): void |
| `state` | [`?State12`](../../doc/models/state-12.md) | Optional | - | getState(): ?State12 | setState(?State12 state): void |

## Example

```php
use DockerLib\Models\Builders\ContainersJsonResponseBuilder;
use DockerLib\Models\Builders\Config3Builder;
use DockerLib\ApiHelper;

$containersJsonResponse = ContainersJsonResponseBuilder::init()
    ->appArmorProfile('AppArmorProfile8')
    ->args(
        [
            'Args4'
        ]
    )
    ->config(
        Config3Builder::init()
            ->argsEscaped(false)
            ->attachStderr(false)
            ->attachStdin(false)
            ->attachStdout(false)
            ->cmd(
                [
                    ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'),
                    ApiHelper::deserialize('{"key1":"val1","key2":"val2"}')
                ]
            )
            ->build()
    )
    ->created('Created8')
    ->driver('Driver0')
    ->build();
```

