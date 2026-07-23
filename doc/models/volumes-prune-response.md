
# Volumes Prune Response

## Structure

`VolumesPruneResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `spaceReclaimed` | `?int` | Optional | Disk space reclaimed in bytes | getSpaceReclaimed(): ?int | setSpaceReclaimed(?int spaceReclaimed): void |
| `volumesDeleted` | `?(string[])` | Optional | Volumes that were deleted | getVolumesDeleted(): ?array | setVolumesDeleted(?array volumesDeleted): void |

## Example

```php
use DockerLib\Models\Builders\VolumesPruneResponseBuilder;

$volumesPruneResponse = VolumesPruneResponseBuilder::init()
    ->spaceReclaimed(230)
    ->volumesDeleted(
        [
            'VolumesDeleted6'
        ]
    )
    ->build();
```

