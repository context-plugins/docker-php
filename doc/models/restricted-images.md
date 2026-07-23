
# Restricted Images

## Structure

`RestrictedImages`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `allowOfficialImages` | `?bool` | Optional | Allow usage of official images if "enabled" is `true`. | getAllowOfficialImages(): ?bool | setAllowOfficialImages(?bool allowOfficialImages): void |
| `allowVerifiedPublishers` | `?bool` | Optional | Allow usage of verified publisher images if "enabled" is `true`. | getAllowVerifiedPublishers(): ?bool | setAllowVerifiedPublishers(?bool allowVerifiedPublishers): void |
| `enabled` | `?bool` | Optional | Whether or not to restrict image usage for users in the organization. | getEnabled(): ?bool | setEnabled(?bool enabled): void |

## Example

```php
use DockerLib\Models\Builders\RestrictedImagesBuilder;

$restrictedImages = RestrictedImagesBuilder::init()
    ->allowOfficialImages(true)
    ->allowVerifiedPublishers(true)
    ->enabled(true)
    ->build();
```

