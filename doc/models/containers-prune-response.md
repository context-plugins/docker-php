
# Containers Prune Response

## Structure

`ContainersPruneResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `containersDeleted` | `?(string[])` | Optional | Container IDs that were deleted | getContainersDeleted(): ?array | setContainersDeleted(?array containersDeleted): void |
| `spaceReclaimed` | `?int` | Optional | Disk space reclaimed in bytes | getSpaceReclaimed(): ?int | setSpaceReclaimed(?int spaceReclaimed): void |

## Example

```php
use DockerLib\Models\Builders\ContainersPruneResponseBuilder;

$containersPruneResponse = ContainersPruneResponseBuilder::init()
    ->containersDeleted(
        [
            'ContainersDeleted5',
            'ContainersDeleted4',
            'ContainersDeleted3'
        ]
    )
    ->spaceReclaimed(30)
    ->build();
```

