
# Mount Point

A mount point inside a container

## Structure

`MountPoint`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `destination` | `?string` | Optional | - | getDestination(): ?string | setDestination(?string destination): void |
| `driver` | `?string` | Optional | - | getDriver(): ?string | setDriver(?string driver): void |
| `mode` | `?string` | Optional | - | getMode(): ?string | setMode(?string mode): void |
| `name` | `?string` | Optional | - | getName(): ?string | setName(?string name): void |
| `propagation` | `?string` | Optional | - | getPropagation(): ?string | setPropagation(?string propagation): void |
| `rW` | `?bool` | Optional | - | getRW(): ?bool | setRW(?bool rW): void |
| `source` | `?string` | Optional | - | getSource(): ?string | setSource(?string source): void |
| `type` | `?string` | Optional | - | getType(): ?string | setType(?string type): void |

## Example

```php
use DockerLib\Models\Builders\MountPointBuilder;

$mountPoint = MountPointBuilder::init()
    ->destination('Destination6')
    ->driver('Driver6')
    ->mode('Mode4')
    ->name('Name0')
    ->propagation('Propagation0')
    ->build();
```

