
# Settings 2

## Structure

`Settings2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `args` | `string[]` | Required | - | getArgs(): array | setArgs(array args): void |
| `devices` | [`PluginDevice[]`](../../doc/models/plugin-device.md) | Required | - | getDevices(): array | setDevices(array devices): void |
| `env` | `string[]` | Required | - | getEnv(): array | setEnv(array env): void |
| `mounts` | [`PluginMount[]`](../../doc/models/plugin-mount.md) | Required | - | getMounts(): array | setMounts(array mounts): void |

## Example

```php
use DockerLib\Models\Builders\Settings2Builder;
use DockerLib\Models\Builders\PluginDeviceBuilder;
use DockerLib\Models\Builders\PluginMountBuilder;

$settings2 = Settings2Builder::init(
    [
        'Args2',
        'Args3',
        'Args4'
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

