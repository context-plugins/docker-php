
# Mode 1

Scheduling mode for the service.

## Structure

`Mode1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `global` | `?array` | Optional | - | getGlobal(): ?array | setGlobal(?array global): void |
| `replicated` | [`?Replicated`](../../doc/models/replicated.md) | Optional | - | getReplicated(): ?Replicated | setReplicated(?Replicated replicated): void |

## Example

```php
use DockerLib\Models\Builders\Mode1Builder;
use DockerLib\ApiHelper;
use DockerLib\Models\Builders\ReplicatedBuilder;

$mode1 = Mode1Builder::init()
    ->global(ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->replicated(
        ReplicatedBuilder::init()
            ->replicas(34)
            ->build()
    )
    ->build();
```

