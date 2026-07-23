
# Config 1

The config of a plugin.

## Structure

`Config1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `args` | [`Args`](../../doc/models/args.md) | Required | - | getArgs(): Args | setArgs(Args args): void |
| `description` | `string` | Required | - | getDescription(): string | setDescription(string description): void |
| `dockerVersion` | `?string` | Optional | Docker Version used to create the plugin | getDockerVersion(): ?string | setDockerVersion(?string dockerVersion): void |
| `documentation` | `string` | Required | - | getDocumentation(): string | setDocumentation(string documentation): void |
| `entrypoint` | `string[]` | Required | - | getEntrypoint(): array | setEntrypoint(array entrypoint): void |
| `env` | [`PluginEnv[]`](../../doc/models/plugin-env.md) | Required | - | getEnv(): array | setEnv(array env): void |
| `interface` | [`Interface2`](../../doc/models/interface-2.md) | Required | - | getInterface(): Interface2 | setInterface(Interface2 interface): void |
| `ipcHost` | `bool` | Required | - | getIpcHost(): bool | setIpcHost(bool ipcHost): void |
| `linux` | [`Linux`](../../doc/models/linux.md) | Required | - | getLinux(): Linux | setLinux(Linux linux): void |
| `mounts` | [`PluginMount[]`](../../doc/models/plugin-mount.md) | Required | - | getMounts(): array | setMounts(array mounts): void |
| `network` | [`Network1`](../../doc/models/network-1.md) | Required | - | getNetwork(): Network1 | setNetwork(Network1 network): void |
| `pidHost` | `bool` | Required | - | getPidHost(): bool | setPidHost(bool pidHost): void |
| `propagatedMount` | `string` | Required | - | getPropagatedMount(): string | setPropagatedMount(string propagatedMount): void |
| `user` | [`?User`](../../doc/models/user.md) | Optional | - | getUser(): ?User | setUser(?User user): void |
| `workDir` | `string` | Required | - | getWorkDir(): string | setWorkDir(string workDir): void |
| `rootfs` | [`?Rootfs1`](../../doc/models/rootfs-1.md) | Optional | - | getRootfs(): ?Rootfs1 | setRootfs(?Rootfs1 rootfs): void |

## Example

```php
use DockerLib\Models\Builders\Config1Builder;
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

$config1 = Config1Builder::init(
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
    ->build();
```

