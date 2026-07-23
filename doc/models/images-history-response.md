
# Images History Response

## Structure

`ImagesHistoryResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `comment` | `string` | Required | - | getComment(): string | setComment(string comment): void |
| `created` | `int` | Required | - | getCreated(): int | setCreated(int created): void |
| `createdBy` | `string` | Required | - | getCreatedBy(): string | setCreatedBy(string createdBy): void |
| `id` | `string` | Required | - | getId(): string | setId(string id): void |
| `size` | `int` | Required | - | getSize(): int | setSize(int size): void |
| `tags` | `string[]` | Required | - | getTags(): array | setTags(array tags): void |

## Example

```php
use DockerLib\Models\Builders\ImagesHistoryResponseBuilder;

$imagesHistoryResponse = ImagesHistoryResponseBuilder::init(
    'Comment6',
    70,
    'CreatedBy4',
    'Id8',
    8,
    [
        'Tags2',
        'Tags1'
    ]
)->build();
```

