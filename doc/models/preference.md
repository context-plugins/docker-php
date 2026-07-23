
# Preference

## Structure

`Preference`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `spread` | [`?Spread`](../../doc/models/spread.md) | Optional | - | getSpread(): ?Spread | setSpread(?Spread spread): void |

## Example

```php
use DockerLib\Models\Builders\PreferenceBuilder;
use DockerLib\Models\Builders\SpreadBuilder;

$preference = PreferenceBuilder::init()
    ->spread(
        SpreadBuilder::init()
            ->spreadDescriptor('SpreadDescriptor2')
            ->build()
    )
    ->build();
```

