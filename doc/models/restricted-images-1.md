
# Restricted Images 1

## Structure

`RestrictedImages1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `allowOfficialImages` | `bool` | Required | Allow usage of official images if "enabled" is `true`. | getAllowOfficialImages(): bool | setAllowOfficialImages(bool allowOfficialImages): void |
| `allowVerifiedPublishers` | `bool` | Required | Allow usage of verified publisher images if "enabled" is `true`. | getAllowVerifiedPublishers(): bool | setAllowVerifiedPublishers(bool allowVerifiedPublishers): void |
| `enabled` | `bool` | Required | Whether or not to restrict image usage for users in the organization. | getEnabled(): bool | setEnabled(bool enabled): void |

## Example

```php
use DockerLib\Models\Builders\RestrictedImages1Builder;

$restrictedImages1 = RestrictedImages1Builder::init(
    true,
    true,
    true
)->build();
```

