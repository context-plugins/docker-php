
# Build Prune Response

## Structure

`BuildPruneResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `spaceReclaimed` | `?int` | Optional | Disk space reclaimed in bytes | getSpaceReclaimed(): ?int | setSpaceReclaimed(?int spaceReclaimed): void |

## Example

```php
use DockerLib\Models\Builders\BuildPruneResponseBuilder;

$buildPruneResponse = BuildPruneResponseBuilder::init()
    ->spaceReclaimed(146)
    ->build();
```

