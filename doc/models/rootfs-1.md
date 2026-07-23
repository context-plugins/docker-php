
# Rootfs 1

## Structure

`Rootfs1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `diffIds` | `?(string[])` | Optional | - | getDiffIds(): ?array | setDiffIds(?array diffIds): void |
| `type` | `?string` | Optional | - | getType(): ?string | setType(?string type): void |

## Example

```php
use DockerLib\Models\Builders\Rootfs1Builder;

$rootfs1 = Rootfs1Builder::init()
    ->diffIds(
        [
            'sha256:675532206fbf3030b8458f88d6e26d4eb1577688a25efec97154c94e8b6b4887',
            'sha256:e216a057b1cb1efc11f8a268f37ef62083e70b1b38323ba252e25ac88904a7e8'
        ]
    )
    ->type('layers')
    ->build();
```

