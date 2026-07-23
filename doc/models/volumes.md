
# Volumes

An object mapping mount point paths inside the container to empty objects.

## Structure

`Volumes`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `additionalProperties` | [`?string(AdditionalPropertiesEnum)`](../../doc/models/additional-properties-enum.md) | Optional | - | getAdditionalProperties(): ?string | setAdditionalProperties(?string additionalProperties): void |

## Example

```php
use DockerLib\Models\Builders\VolumesBuilder;
use DockerLib\Models\AdditionalPropertiesEnum;

$volumes = VolumesBuilder::init()
    ->additionalProperties(AdditionalPropertiesEnum::ENUM_0)
    ->build();
```

