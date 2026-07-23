
# Image

## Structure

`Image`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `architecture` | `string` | Required | - | getArchitecture(): string | setArchitecture(string architecture): void |
| `author` | `string` | Required | - | getAuthor(): string | setAuthor(string author): void |
| `comment` | `string` | Required | - | getComment(): string | setComment(string comment): void |
| `config` | [`?Config3`](../../doc/models/config-3.md) | Optional | - | getConfig(): ?Config3 | setConfig(?Config3 config): void |
| `container` | `string` | Required | - | getContainer(): string | setContainer(string container): void |
| `containerConfig` | [`?ContainerConfig1`](../../doc/models/container-config-1.md) | Optional | - | getContainerConfig(): ?ContainerConfig1 | setContainerConfig(?ContainerConfig1 containerConfig): void |
| `created` | `string` | Required | - | getCreated(): string | setCreated(string created): void |
| `dockerVersion` | `string` | Required | - | getDockerVersion(): string | setDockerVersion(string dockerVersion): void |
| `graphDriver` | [`GraphDriver`](../../doc/models/graph-driver.md) | Required | - | getGraphDriver(): GraphDriver | setGraphDriver(GraphDriver graphDriver): void |
| `id` | `string` | Required | - | getId(): string | setId(string id): void |
| `metadata` | [`?Metadata`](../../doc/models/metadata.md) | Optional | - | getMetadata(): ?Metadata | setMetadata(?Metadata metadata): void |
| `os` | `string` | Required | - | getOs(): string | setOs(string os): void |
| `osVersion` | `?string` | Optional | - | getOsVersion(): ?string | setOsVersion(?string osVersion): void |
| `parent` | `string` | Required | - | getParent(): string | setParent(string parent): void |
| `repoDigests` | `?(string[])` | Optional | - | getRepoDigests(): ?array | setRepoDigests(?array repoDigests): void |
| `repoTags` | `?(string[])` | Optional | - | getRepoTags(): ?array | setRepoTags(?array repoTags): void |
| `rootFS` | [`RootFS`](../../doc/models/root-fs.md) | Required | - | getRootFS(): RootFS | setRootFS(RootFS rootFS): void |
| `size` | `int` | Required | - | getSize(): int | setSize(int size): void |
| `virtualSize` | `int` | Required | - | getVirtualSize(): int | setVirtualSize(int virtualSize): void |

## Example

```php
use DockerLib\Models\Builders\ImageBuilder;
use DockerLib\Models\Builders\GraphDriverBuilder;
use DockerLib\Models\Builders\RootFSBuilder;
use DockerLib\Models\Builders\Config3Builder;
use DockerLib\ApiHelper;
use DockerLib\Models\Builders\ContainerConfig1Builder;
use DockerLib\Models\Builders\MetadataBuilder;

$image = ImageBuilder::init(
    'Architecture8',
    'Author2',
    'Comment0',
    'Container2',
    'Created4',
    'DockerVersion0',
    GraphDriverBuilder::init(
        [
            'key0' => 'Data0',
            'key1' => 'Data1',
            'key2' => 'Data2'
        ],
        'Name4'
    )->build(),
    'Id2',
    'Os0',
    'Parent8',
    RootFSBuilder::init(
        'Type8'
    )
        ->baseLayer('BaseLayer6')
        ->layers(
            [
                'Layers3',
                'Layers4'
            ]
        )
        ->build(),
    238,
    246
)
    ->config(
        Config3Builder::init()
            ->argsEscaped(false)
            ->attachStderr(false)
            ->attachStdin(false)
            ->attachStdout(false)
            ->cmd(
                [
                    ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'),
                    ApiHelper::deserialize('{"key1":"val1","key2":"val2"}')
                ]
            )
            ->build()
    )
    ->containerConfig(
        ContainerConfig1Builder::init()
            ->argsEscaped(false)
            ->attachStderr(false)
            ->attachStdin(false)
            ->attachStdout(false)
            ->cmd(
                [
                    ApiHelper::deserialize('{"key1":"val1","key2":"val2"}')
                ]
            )
            ->build()
    )
    ->metadata(
        MetadataBuilder::init()
            ->lastTagTime('LastTagTime6')
            ->build()
    )
    ->osVersion('OsVersion8')
    ->repoDigests(
        [
            'RepoDigests0'
        ]
    )
    ->build();
```

