
# Create Access Token Request

## Structure

`CreateAccessTokenRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `scopes` | `string[]` | Required | Valid scopes: "repo:admin", "repo:write", "repo:read", "repo:public_read" | getScopes(): array | setScopes(array scopes): void |
| `tokenLabel` | `string` | Required | Friendly name for you to identify the token. | getTokenLabel(): string | setTokenLabel(string tokenLabel): void |

## Example

```php
use DockerLib\Models\Builders\CreateAccessTokenRequestBuilder;

$createAccessTokenRequest = CreateAccessTokenRequestBuilder::init(
    [
        'repo:read'
    ],
    'My read only token'
)->build();
```

