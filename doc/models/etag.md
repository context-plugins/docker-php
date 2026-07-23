
# Etag

## Structure

`Etag`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `supported` | `?bool` | Optional | - | getSupported(): ?bool | setSupported(?bool supported): void |

## Example

```php
use DockerLib\Models\Builders\EtagBuilder;

$etag = EtagBuilder::init()
    ->supported(false)
    ->build();
```

