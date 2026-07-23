
# Device Mapping

A device mapping between the host and container

## Structure

`DeviceMapping`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cgroupPermissions` | `?string` | Optional | - | getCgroupPermissions(): ?string | setCgroupPermissions(?string cgroupPermissions): void |
| `pathInContainer` | `?string` | Optional | - | getPathInContainer(): ?string | setPathInContainer(?string pathInContainer): void |
| `pathOnHost` | `?string` | Optional | - | getPathOnHost(): ?string | setPathOnHost(?string pathOnHost): void |

## Example

```php
use DockerLib\Models\Builders\DeviceMappingBuilder;

$deviceMapping = DeviceMappingBuilder::init()
    ->cgroupPermissions('mrw')
    ->pathInContainer('/dev/deviceName')
    ->pathOnHost('/dev/deviceName')
    ->build();
```

