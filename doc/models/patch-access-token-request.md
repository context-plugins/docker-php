
# Patch Access Token Request

## Structure

`PatchAccessTokenRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `isActive` | `?bool` | Optional | - | getIsActive(): ?bool | setIsActive(?bool isActive): void |
| `tokenLabel` | `?string` | Optional | - | getTokenLabel(): ?string | setTokenLabel(?string tokenLabel): void |

## Example

```php
use DockerLib\Models\Builders\PatchAccessTokenRequestBuilder;

$patchAccessTokenRequest = PatchAccessTokenRequestBuilder::init()
    ->isActive(false)
    ->tokenLabel('My read only token')
    ->build();
```

