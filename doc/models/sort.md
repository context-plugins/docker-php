
# Sort

## Structure

`Sort`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `supported` | `?bool` | Optional | - | getSupported(): ?bool | setSupported(?bool supported): void |

## Example

```php
use DockerLib\Models\Builders\SortBuilder;

$sort = SortBuilder::init()
    ->supported(true)
    ->build();
```

