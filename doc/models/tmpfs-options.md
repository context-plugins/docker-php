
# Tmpfs Options

Optional configuration for the `tmpfs` type.

## Structure

`TmpfsOptions`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `mode` | `?int` | Optional | The permission mode for the tmpfs mount in an integer. | getMode(): ?int | setMode(?int mode): void |
| `sizeBytes` | `?int` | Optional | The size for the tmpfs mount in bytes. | getSizeBytes(): ?int | setSizeBytes(?int sizeBytes): void |

## Example

```php
use DockerLib\Models\Builders\TmpfsOptionsBuilder;

$tmpfsOptions = TmpfsOptionsBuilder::init()
    ->mode(46)
    ->sizeBytes(60)
    ->build();
```

