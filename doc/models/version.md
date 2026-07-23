
# Version

## Structure

`Version`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `index` | `?int` | Optional | - | getIndex(): ?int | setIndex(?int index): void |

## Example

```php
use DockerLib\Models\Builders\VersionBuilder;

$version = VersionBuilder::init()
    ->index(373531)
    ->build();
```

