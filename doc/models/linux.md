
# Linux

## Structure

`Linux`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `allowAllDevices` | `bool` | Required | - | getAllowAllDevices(): bool | setAllowAllDevices(bool allowAllDevices): void |
| `capabilities` | `string[]` | Required | - | getCapabilities(): array | setCapabilities(array capabilities): void |
| `devices` | [`PluginDevice[]`](../../doc/models/plugin-device.md) | Required | - | getDevices(): array | setDevices(array devices): void |

## Example

```php
use DockerLib\Models\Builders\LinuxBuilder;
use DockerLib\Models\Builders\PluginDeviceBuilder;

$linux = LinuxBuilder::init(
    false,
    [
        'CAP_SYS_ADMIN',
        'CAP_SYSLOG'
    ],
    [
        PluginDeviceBuilder::init(
            'Description2',
            'Name4',
            '/dev/fuse',
            [
                'Settable3',
                'Settable4',
                'Settable5'
            ]
        )->build()
    ]
)->build();
```

