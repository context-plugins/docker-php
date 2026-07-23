
# Patch

## Structure

`Patch`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `supported` | `?bool` | Optional | - | getSupported(): ?bool | setSupported(?bool supported): void |

## Example

```php
use DockerLib\Models\Builders\PatchBuilder;

$patch = PatchBuilder::init()
    ->supported(false)
    ->build();
```

