
# Task Template

## Structure

`TaskTemplate`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `containerSpec` | [`?ContainerSpec2`](../../doc/models/container-spec-2.md) | Optional | - | getContainerSpec(): ?ContainerSpec2 | setContainerSpec(?ContainerSpec2 containerSpec): void |
| `forceUpdate` | `?int` | Optional | A counter that triggers an update even if no relevant parameters have been changed. | getForceUpdate(): ?int | setForceUpdate(?int forceUpdate): void |
| `logDriver` | [`?LogDriver12`](../../doc/models/log-driver-12.md) | Optional | - | getLogDriver(): ?LogDriver12 | setLogDriver(?LogDriver12 logDriver): void |
| `networks` | [`?(Network2[])`](../../doc/models/network-2.md) | Optional | - | getNetworks(): ?array | setNetworks(?array networks): void |
| `placement` | [`?Placement`](../../doc/models/placement.md) | Optional | - | getPlacement(): ?Placement | setPlacement(?Placement placement): void |
| `pluginSpec` | [`?PluginSpec2`](../../doc/models/plugin-spec-2.md) | Optional | - | getPluginSpec(): ?PluginSpec2 | setPluginSpec(?PluginSpec2 pluginSpec): void |
| `resources` | [`?Resources2`](../../doc/models/resources-2.md) | Optional | - | getResources(): ?Resources2 | setResources(?Resources2 resources): void |
| `restartPolicy` | [`?RestartPolicy2`](../../doc/models/restart-policy-2.md) | Optional | - | getRestartPolicy(): ?RestartPolicy2 | setRestartPolicy(?RestartPolicy2 restartPolicy): void |
| `runtime` | `?string` | Optional | Runtime is the type of runtime specified for the task executor. | getRuntime(): ?string | setRuntime(?string runtime): void |

## Example

```php
use DockerLib\Models\Builders\TaskTemplateBuilder;
use DockerLib\Models\Builders\ContainerSpec2Builder;
use DockerLib\Models\Builders\Config2Builder;
use DockerLib\Models\Builders\File1Builder;
use DockerLib\Models\Builders\DNSConfig2Builder;
use DockerLib\Models\Builders\LogDriver12Builder;
use DockerLib\Models\Builders\Network2Builder;
use DockerLib\Models\Builders\PlacementBuilder;
use DockerLib\Models\Builders\PlatformBuilder;

$taskTemplate = TaskTemplateBuilder::init()
    ->containerSpec(
        ContainerSpec2Builder::init()
            ->args(
                [
                    'Args4',
                    'Args5'
                ]
            )
            ->command(
                [
                    'Command2'
                ]
            )
            ->configs(
                [
                    Config2Builder::init()
                        ->configID('ConfigID0')
                        ->configName('ConfigName2')
                        ->file(
                            File1Builder::init()
                                ->gID('GID0')
                                ->mode(224)
                                ->name('Name0')
                                ->uID('UID0')
                                ->build()
                        )
                        ->build(),
                    Config2Builder::init()
                        ->configID('ConfigID0')
                        ->configName('ConfigName2')
                        ->file(
                            File1Builder::init()
                                ->gID('GID0')
                                ->mode(224)
                                ->name('Name0')
                                ->uID('UID0')
                                ->build()
                        )
                        ->build()
                ]
            )
            ->dNSConfig(
                DNSConfig2Builder::init()
                    ->nameservers(
                        [
                            'Nameservers4',
                            'Nameservers3'
                        ]
                    )
                    ->options(
                        [
                            'Options6'
                        ]
                    )
                    ->search(
                        [
                            'Search7'
                        ]
                    )
                    ->build()
            )
            ->dir('Dir0')
            ->build()
    )
    ->forceUpdate(14)
    ->logDriver(
        LogDriver12Builder::init()
            ->name('Name8')
            ->options(
                [
                    'key0' => 'Options0'
                ]
            )
            ->build()
    )
    ->networks(
        [
            Network2Builder::init()
                ->aliases(
                    [
                        'Aliases6',
                        'Aliases5',
                        'Aliases4'
                    ]
                )
                ->target('Target8')
                ->build(),
            Network2Builder::init()
                ->aliases(
                    [
                        'Aliases6',
                        'Aliases5',
                        'Aliases4'
                    ]
                )
                ->target('Target8')
                ->build()
        ]
    )
    ->placement(
        PlacementBuilder::init()
            ->constraints(
                [
                    'Constraints7',
                    'Constraints8'
                ]
            )
            ->platforms(
                [
                    PlatformBuilder::init()
                        ->architecture('Architecture2')
                        ->oS('OS0')
                        ->build(),
                    PlatformBuilder::init()
                        ->architecture('Architecture2')
                        ->oS('OS0')
                        ->build()
                ]
            )
            ->preferences(
                [
                    null
                ]
            )
            ->build()
    )
    ->build();
```

