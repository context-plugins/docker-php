
# Container Summary

## Structure

`ContainerSummary`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `command` | `?string` | Optional | Command to run when starting the container | getCommand(): ?string | setCommand(?string command): void |
| `created` | `?int` | Optional | When the container was created | getCreated(): ?int | setCreated(?int created): void |
| `hostConfig` | [`?HostConfig2`](../../doc/models/host-config-2.md) | Optional | - | getHostConfig(): ?HostConfig2 | setHostConfig(?HostConfig2 hostConfig): void |
| `id` | `?string` | Optional | The ID of this container | getId(): ?string | setId(?string id): void |
| `image` | `?string` | Optional | The name of the image used when creating this container | getImage(): ?string | setImage(?string image): void |
| `imageID` | `?string` | Optional | The ID of the image that this container was created from | getImageID(): ?string | setImageID(?string imageID): void |
| `labels` | `?array<string,string>` | Optional | User-defined key/value metadata. | getLabels(): ?array | setLabels(?array labels): void |
| `mounts` | [`?(Mount[])`](../../doc/models/mount.md) | Optional | - | getMounts(): ?array | setMounts(?array mounts): void |
| `names` | `?(string[])` | Optional | The names that this container has been given | getNames(): ?array | setNames(?array names): void |
| `networkSettings` | [`?NetworkSettings22`](../../doc/models/network-settings-22.md) | Optional | - | getNetworkSettings(): ?NetworkSettings22 | setNetworkSettings(?NetworkSettings22 networkSettings): void |
| `ports` | [`?(Port[])`](../../doc/models/port.md) | Optional | The ports exposed by this container | getPorts(): ?array | setPorts(?array ports): void |
| `sizeRootFs` | `?int` | Optional | The total size of all the files in this container | getSizeRootFs(): ?int | setSizeRootFs(?int sizeRootFs): void |
| `sizeRw` | `?int` | Optional | The size of files that have been created or changed by this container | getSizeRw(): ?int | setSizeRw(?int sizeRw): void |
| `state` | `?string` | Optional | The state of this container (e.g. `Exited`) | getState(): ?string | setState(?string state): void |
| `status` | `?string` | Optional | Additional human-readable status of this container (e.g. `Exit 0`) | getStatus(): ?string | setStatus(?string status): void |

## Example

```php
use DockerLib\Models\Builders\ContainerSummaryBuilder;
use DockerLib\Models\Builders\HostConfig2Builder;

$containerSummary = ContainerSummaryBuilder::init()
    ->command('Command2')
    ->created(186)
    ->hostConfig(
        HostConfig2Builder::init()
            ->networkMode('NetworkMode4')
            ->build()
    )
    ->id('Id8')
    ->image('Image8')
    ->build();
```

