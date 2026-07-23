
# Settings

Settings that can be modified by users.

## Structure

`Settings`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `args` | `string[]` | Required | - | getArgs(): array | setArgs(array args): void |
| `devices` | [`PluginDevice[]`](../../doc/models/plugin-device.md) | Required | - | getDevices(): array | setDevices(array devices): void |
| `env` | `string[]` | Required | - | getEnv(): array | setEnv(array env): void |
| `mounts` | [`PluginMount[]`](../../doc/models/plugin-mount.md) | Required | - | getMounts(): array | setMounts(array mounts): void |

## Example

```php
use DockerLib\Models\Builders\SettingsBuilder;
use DockerLib\Models\Builders\PluginDeviceBuilder;
use DockerLib\Models\Builders\PluginMountBuilder;

$settings = SettingsBuilder::init(
    [
        'Args8',
        'Args9',
        'Args0'
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
    ],
    [
        'DEBUG=0'
    ],
    [
        PluginMountBuilder::init(
            'This is a mount that\'s used by the plugin.',
            '/mnt/state',
            'some-mount',
            [
                'rbind',
                'rw'
            ],
            [
                'Settable1',
                'Settable2'
            ],
            '/var/lib/docker/plugins/',
            'bind'
        )->build()
    ]
)->build();
```

