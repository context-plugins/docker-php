
# Image Summary

## Structure

`ImageSummary`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `containers` | `int` | Required | - | getContainers(): int | setContainers(int containers): void |
| `created` | `int` | Required | - | getCreated(): int | setCreated(int created): void |
| `id` | `string` | Required | - | getId(): string | setId(string id): void |
| `labels` | `array<string,string>` | Required | - | getLabels(): array | setLabels(array labels): void |
| `parentId` | `string` | Required | - | getParentId(): string | setParentId(string parentId): void |
| `repoDigests` | `string[]` | Required | - | getRepoDigests(): array | setRepoDigests(array repoDigests): void |
| `repoTags` | `string[]` | Required | - | getRepoTags(): array | setRepoTags(array repoTags): void |
| `sharedSize` | `int` | Required | - | getSharedSize(): int | setSharedSize(int sharedSize): void |
| `size` | `int` | Required | - | getSize(): int | setSize(int size): void |
| `virtualSize` | `int` | Required | - | getVirtualSize(): int | setVirtualSize(int virtualSize): void |

## Example

```php
use DockerLib\Models\Builders\ImageSummaryBuilder;

$imageSummary = ImageSummaryBuilder::init(
    12,
    106,
    'Id6',
    [
        'key0' => 'Labels8',
        'key1' => 'Labels9',
        'key2' => 'Labels0'
    ],
    'ParentId8',
    [
        'RepoDigests4',
        'RepoDigests5',
        'RepoDigests6'
    ],
    [
        'RepoTags8'
    ],
    102,
    44,
    52
)->build();
```

