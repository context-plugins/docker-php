
# Bulk

## Structure

`Bulk`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `maxOperations` | `?int` | Optional | - | getMaxOperations(): ?int | setMaxOperations(?int maxOperations): void |
| `maxPayloadSize` | `?int` | Optional | - | getMaxPayloadSize(): ?int | setMaxPayloadSize(?int maxPayloadSize): void |
| `supported` | `?bool` | Optional | - | getSupported(): ?bool | setSupported(?bool supported): void |

## Example

```php
use DockerLib\Models\Builders\BulkBuilder;

$bulk = BulkBuilder::init()
    ->maxOperations(148)
    ->maxPayloadSize(104)
    ->supported(false)
    ->build();
```

