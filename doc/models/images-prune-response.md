
# Images Prune Response

## Structure

`ImagesPruneResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `imagesDeleted` | [`?(ImageDeleteResponseItem[])`](../../doc/models/image-delete-response-item.md) | Optional | Images that were deleted | getImagesDeleted(): ?array | setImagesDeleted(?array imagesDeleted): void |
| `spaceReclaimed` | `?int` | Optional | Disk space reclaimed in bytes | getSpaceReclaimed(): ?int | setSpaceReclaimed(?int spaceReclaimed): void |

## Example

```php
use DockerLib\Models\Builders\ImagesPruneResponseBuilder;
use DockerLib\Models\Builders\ImageDeleteResponseItemBuilder;

$imagesPruneResponse = ImagesPruneResponseBuilder::init()
    ->imagesDeleted(
        [
            ImageDeleteResponseItemBuilder::init()
                ->deleted('Deleted8')
                ->untagged('Untagged4')
                ->build(),
            ImageDeleteResponseItemBuilder::init()
                ->deleted('Deleted8')
                ->untagged('Untagged4')
                ->build(),
            ImageDeleteResponseItemBuilder::init()
                ->deleted('Deleted8')
                ->untagged('Untagged4')
                ->build()
        ]
    )
    ->spaceReclaimed(172)
    ->build();
```

