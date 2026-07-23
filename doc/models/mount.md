
# Mount

## Structure

`Mount`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `bindOptions` | [`?BindOptions2`](../../doc/models/bind-options-2.md) | Optional | - | getBindOptions(): ?BindOptions2 | setBindOptions(?BindOptions2 bindOptions): void |
| `consistency` | `?string` | Optional | The consistency requirement for the mount: `default`, `consistent`, `cached`, or `delegated`. | getConsistency(): ?string | setConsistency(?string consistency): void |
| `readOnly` | `?bool` | Optional | Whether the mount should be read-only. | getReadOnly(): ?bool | setReadOnly(?bool readOnly): void |
| `source` | `?string` | Optional | Mount source (e.g. a volume name, a host path). | getSource(): ?string | setSource(?string source): void |
| `target` | `?string` | Optional | Container path. | getTarget(): ?string | setTarget(?string target): void |
| `tmpfsOptions` | [`?TmpfsOptions2`](../../doc/models/tmpfs-options-2.md) | Optional | - | getTmpfsOptions(): ?TmpfsOptions2 | setTmpfsOptions(?TmpfsOptions2 tmpfsOptions): void |
| `type` | [`?string(TypeEnum)`](../../doc/models/type-enum.md) | Optional | - | getType(): ?string | setType(?string type): void |
| `volumeOptions` | [`?VolumeOptions2`](../../doc/models/volume-options-2.md) | Optional | - | getVolumeOptions(): ?VolumeOptions2 | setVolumeOptions(?VolumeOptions2 volumeOptions): void |

## Example

```php
use DockerLib\Models\Builders\MountBuilder;
use DockerLib\Models\Builders\BindOptions2Builder;
use DockerLib\Models\PropagationEnum;

$mount = MountBuilder::init()
    ->bindOptions(
        BindOptions2Builder::init()
            ->propagation(PropagationEnum::PRIVATE_)
            ->build()
    )
    ->consistency('Consistency4')
    ->readOnly(false)
    ->source('Source2')
    ->target('Target6')
    ->build();
```

