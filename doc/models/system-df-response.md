
# System Df Response

## Structure

`SystemDfResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `containers` | [`?(ContainerSummary[][])`](../../doc/models/container-summary.md) | Optional | - | getContainers(): ?array | setContainers(?array containers): void |
| `images` | [`?(ImageSummary[])`](../../doc/models/image-summary.md) | Optional | - | getImages(): ?array | setImages(?array images): void |
| `layersSize` | `?int` | Optional | - | getLayersSize(): ?int | setLayersSize(?int layersSize): void |
| `volumes` | [`?(Volume[])`](../../doc/models/volume.md) | Optional | - | getVolumes(): ?array | setVolumes(?array volumes): void |

## Example

```php
use DockerLib\Models\Builders\SystemDfResponseBuilder;
use DockerLib\Models\Builders\ContainerSummaryBuilder;
use DockerLib\Models\Builders\HostConfig2Builder;
use DockerLib\ApiHelper;
use DockerLib\Models\Builders\ImageSummaryBuilder;
use DockerLib\Models\Builders\VolumeBuilder;
use DockerLib\Models\ScopeEnum;

$systemDfResponse = SystemDfResponseBuilder::init()
    ->containers(
        [
            [
                ContainerSummaryBuilder::init()
                    ->command('Command2')
                    ->created(118)
                    ->hostConfig(
                        HostConfig2Builder::init()
                            ->networkMode('NetworkMode4')
                            ->build()
                    )
                    ->id('Id2')
                    ->image('Image2')
                    ->build(),
                ContainerSummaryBuilder::init()
                    ->command('Command2')
                    ->created(118)
                    ->hostConfig(
                        HostConfig2Builder::init()
                            ->networkMode('NetworkMode4')
                            ->build()
                    )
                    ->id('Id2')
                    ->image('Image2')
                    ->build(),
                ContainerSummaryBuilder::init()
                    ->command('Command2')
                    ->created(118)
                    ->hostConfig(
                        HostConfig2Builder::init()
                            ->networkMode('NetworkMode4')
                            ->build()
                    )
                    ->id('Id2')
                    ->image('Image2')
                    ->build()
            ],
            [
                ContainerSummaryBuilder::init()
                    ->command('Command2')
                    ->created(118)
                    ->hostConfig(
                        HostConfig2Builder::init()
                            ->networkMode('NetworkMode4')
                            ->build()
                    )
                    ->id('Id2')
                    ->image('Image2')
                    ->build(),
                ContainerSummaryBuilder::init()
                    ->command('Command2')
                    ->created(118)
                    ->hostConfig(
                        HostConfig2Builder::init()
                            ->networkMode('NetworkMode4')
                            ->build()
                    )
                    ->id('Id2')
                    ->image('Image2')
                    ->build(),
                ContainerSummaryBuilder::init()
                    ->command('Command2')
                    ->created(118)
                    ->hostConfig(
                        HostConfig2Builder::init()
                            ->networkMode('NetworkMode4')
                            ->build()
                    )
                    ->id('Id2')
                    ->image('Image2')
                    ->build()
            ],
            [
                ContainerSummaryBuilder::init()
                    ->command('Command2')
                    ->created(118)
                    ->hostConfig(
                        HostConfig2Builder::init()
                            ->networkMode('NetworkMode4')
                            ->build()
                    )
                    ->id('Id2')
                    ->image('Image2')
                    ->build(),
                ContainerSummaryBuilder::init()
                    ->command('Command2')
                    ->created(118)
                    ->hostConfig(
                        HostConfig2Builder::init()
                            ->networkMode('NetworkMode4')
                            ->build()
                    )
                    ->id('Id2')
                    ->image('Image2')
                    ->build(),
                ContainerSummaryBuilder::init()
                    ->command('Command2')
                    ->created(118)
                    ->hostConfig(
                        HostConfig2Builder::init()
                            ->networkMode('NetworkMode4')
                            ->build()
                    )
                    ->id('Id2')
                    ->image('Image2')
                    ->build()
            ]
        ]
    )
    ->images(
        [
            ImageSummaryBuilder::init(
                88,
                226,
                'Id8',
                [
                    'key0' => 'Labels2',
                    'key1' => 'Labels3',
                    'key2' => 'Labels4'
                ],
                'ParentId0',
                [
                    'RepoDigests0',
                    'RepoDigests9',
                    'RepoDigests8'
                ],
                [
                    'RepoTags0',
                    'RepoTags1',
                    'RepoTags2'
                ],
                26,
                224,
                232
            )->build(),
            ImageSummaryBuilder::init(
                88,
                226,
                'Id8',
                [
                    'key0' => 'Labels2',
                    'key1' => 'Labels3',
                    'key2' => 'Labels4'
                ],
                'ParentId0',
                [
                    'RepoDigests0',
                    'RepoDigests9',
                    'RepoDigests8'
                ],
                [
                    'RepoTags0',
                    'RepoTags1',
                    'RepoTags2'
                ],
                26,
                224,
                232
            )->build()
        ]
    )
    ->layersSize(88)
    ->volumes(
        [
            VolumeBuilder::init(
                'Driver8',
                [
                    'key0' => 'Labels8',
                    'key1' => 'Labels9',
                    'key2' => 'Labels0'
                ],
                'Mountpoint4',
                'Name4',
                [
                    'key0' => 'Options0'
                ],
                ScopeEnum::LOCAL
            )
                ->createdAt('CreatedAt6')
                ->status(
                    [
                        'key0' => ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'),
                        'key1' => ApiHelper::deserialize('{"key1":"val1","key2":"val2"}')
                    ]
                )
                ->usageData(ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            VolumeBuilder::init(
                'Driver8',
                [
                    'key0' => 'Labels8',
                    'key1' => 'Labels9',
                    'key2' => 'Labels0'
                ],
                'Mountpoint4',
                'Name4',
                [
                    'key0' => 'Options0'
                ],
                ScopeEnum::LOCAL
            )
                ->createdAt('CreatedAt6')
                ->status(
                    [
                        'key0' => ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'),
                        'key1' => ApiHelper::deserialize('{"key1":"val1","key2":"val2"}')
                    ]
                )
                ->usageData(ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->build();
```

