
# V2 Orgs Settings Request

## Structure

`V2OrgsSettingsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `restrictedImages` | [`RestrictedImages1`](../../doc/models/restricted-images-1.md) | Required | - | getRestrictedImages(): RestrictedImages1 | setRestrictedImages(RestrictedImages1 restrictedImages): void |

## Example

```php
use DockerLib\Models\Builders\V2OrgsSettingsRequestBuilder;
use DockerLib\Models\Builders\RestrictedImages1Builder;

$v2OrgsSettingsRequest = V2OrgsSettingsRequestBuilder::init(
    RestrictedImages1Builder::init(
        true,
        true,
        true
    )->build()
)->build();
```

