
# Plugin

A plugin for the Engine API

## Structure

`Plugin`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `config` | [`Config22`](../../doc/models/config-22.md) | Required | - | getConfig(): Config22 | setConfig(Config22 config): void |
| `enabled` | `bool` | Required | True if the plugin is running. False if the plugin is not running, only installed. | getEnabled(): bool | setEnabled(bool enabled): void |
| `id` | `?string` | Optional | - | getId(): ?string | setId(?string id): void |
| `name` | `string` | Required | - | getName(): string | setName(string name): void |
| `pluginReference` | `?string` | Optional | plugin remote reference used to push/pull the plugin | getPluginReference(): ?string | setPluginReference(?string pluginReference): void |
| `settings` | [`Settings2`](../../doc/models/settings-2.md) | Required | - | getSettings(): Settings2 | setSettings(Settings2 settings): void |

## Example

```php
use DockerLib\Models\Builders\PluginBuilder;
use DockerLib\Models\Builders\Config22Builder;
use DockerLib\Models\Builders\ArgsBuilder;
use DockerLib\Models\Builders\PluginEnvBuilder;
use DockerLib\Models\Builders\Interface2Builder;
use DockerLib\Models\Builders\PluginInterfaceTypeBuilder;
use DockerLib\Models\Builders\LinuxBuilder;
use DockerLib\Models\Builders\PluginDeviceBuilder;
use DockerLib\Models\Builders\PluginMountBuilder;
use DockerLib\Models\Builders\Network1Builder;
use DockerLib\Models\Builders\UserBuilder;
use DockerLib\Models\Builders\Rootfs1Builder;
use DockerLib\Models\Builders\Settings2Builder;

$plugin = PluginBuilder::init(
    Config22Builder::init(
        ArgsBuilder::init(
            'command line arguments',
            'args',
            [
                'Settable9',
                'Settable0',
                'Settable1'
            ],
            [
                'Value6'
            ]
        )->build(),
        'A sample volume plugin for Docker',
        'https://docs.docker.com/engine/extend/plugins/',
        [
            '/usr/bin/sample-volume-plugin',
            '/data'
        ],
        [
            PluginEnvBuilder::init(
                'Description8',
                'Name4',
                [
                    'Settable3'
                ],
                'Value8'
            )->build()
        ],
        Interface2Builder::init(
            'plugins.sock',
            [
                PluginInterfaceTypeBuilder::init(
                    'Capability4',
                    'Prefix0',
                    'Version8'
                )->build()
            ]
        )->build(),
        false,
        LinuxBuilder::init(
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
        )->build(),
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
        ],
        Network1Builder::init(
            'host'
        )->build(),
        false,
        '/mnt/volumes',
        '/bin/'
    )
        ->dockerVersion('17.06.0-ce')
        ->user(
            UserBuilder::init()
                ->gID(214)
                ->uID(176)
                ->build()
        )
        ->rootfs(
            Rootfs1Builder::init()
                ->diffIds(
                    [
                        'diff_ids8',
                        'diff_ids7'
                    ]
                )
                ->type('type4')
                ->build()
        )
        ->build(),
    true,
    'tiborvass/sample-volume-plugin',
    Settings2Builder::init(
        [
            'Args0',
            'Args1'
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
    )->build()
)
    ->id('5724e2c8652da337ab2eedd19fc6fc0ec908e4bd907c7421bf6a8dfc70c4c078')
    ->pluginReference('localhost:5000/tiborvass/sample-volume-plugin:latest')
    ->build();
```

