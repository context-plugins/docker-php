
# Org Settings

## Structure

`OrgSettings`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `restrictedImages` | [`?RestrictedImages`](../../doc/models/restricted-images.md) | Optional | - | getRestrictedImages(): ?RestrictedImages | setRestrictedImages(?RestrictedImages restrictedImages): void |

## Example

```php
use DockerLib\Models\Builders\OrgSettingsBuilder;
use DockerLib\Models\Builders\RestrictedImagesBuilder;

$orgSettings = OrgSettingsBuilder::init()
    ->restrictedImages(
        RestrictedImagesBuilder::init()
            ->allowOfficialImages(false)
            ->allowVerifiedPublishers(false)
            ->enabled(false)
            ->build()
    )
    ->build();
```

