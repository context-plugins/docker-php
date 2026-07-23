
# Filter

## Structure

`Filter`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `maxResults` | `?int` | Optional | - | getMaxResults(): ?int | setMaxResults(?int maxResults): void |
| `supported` | `?bool` | Optional | - | getSupported(): ?bool | setSupported(?bool supported): void |

## Example

```php
use DockerLib\Models\Builders\FilterBuilder;

$filter = FilterBuilder::init()
    ->maxResults(99999)
    ->supported(true)
    ->build();
```

