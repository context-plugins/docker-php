
# Volumes 1

## Structure

`Volumes1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `additionalProperties` | [`?string(AdditionalPropertiesEnum)`](../../doc/models/additional-properties-enum.md) | Optional | - | getAdditionalProperties(): ?string | setAdditionalProperties(?string additionalProperties): void |

## Example

```php
use DockerLib\Models\Builders\Volumes1Builder;
use DockerLib\Models\AdditionalPropertiesEnum;

$volumes1 = Volumes1Builder::init()
    ->additionalProperties(AdditionalPropertiesEnum::ENUM_0)
    ->build();
```

