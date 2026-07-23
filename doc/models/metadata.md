
# Metadata

## Structure

`Metadata`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `lastTagTime` | `?string` | Optional | - | getLastTagTime(): ?string | setLastTagTime(?string lastTagTime): void |

## Example

```php
use DockerLib\Models\Builders\MetadataBuilder;

$metadata = MetadataBuilder::init()
    ->lastTagTime('LastTagTime4')
    ->build();
```

