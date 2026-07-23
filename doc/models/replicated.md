
# Replicated

## Structure

`Replicated`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `replicas` | `?int` | Optional | - | getReplicas(): ?int | setReplicas(?int replicas): void |

## Example

```php
use DockerLib\Models\Builders\ReplicatedBuilder;

$replicated = ReplicatedBuilder::init()
    ->replicas(204)
    ->build();
```

