
# Networks Prune Response

## Structure

`NetworksPruneResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `networksDeleted` | `?(string[])` | Optional | Networks that were deleted | getNetworksDeleted(): ?array | setNetworksDeleted(?array networksDeleted): void |

## Example

```php
use DockerLib\Models\Builders\NetworksPruneResponseBuilder;

$networksPruneResponse = NetworksPruneResponseBuilder::init()
    ->networksDeleted(
        [
            'NetworksDeleted3',
            'NetworksDeleted2'
        ]
    )
    ->build();
```

