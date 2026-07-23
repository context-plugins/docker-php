
# Tmpfs Options 2

## Structure

`TmpfsOptions2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `mode` | `?int` | Optional | The permission mode for the tmpfs mount in an integer. | getMode(): ?int | setMode(?int mode): void |
| `sizeBytes` | `?int` | Optional | The size for the tmpfs mount in bytes. | getSizeBytes(): ?int | setSizeBytes(?int sizeBytes): void |

## Example

```php
use DockerLib\Models\Builders\TmpfsOptions2Builder;

$tmpfsOptions2 = TmpfsOptions2Builder::init()
    ->mode(186)
    ->sizeBytes(200)
    ->build();
```

