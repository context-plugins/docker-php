
# Access Token

## Structure

`AccessToken`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `clientId` | `?string` | Optional | - | getClientId(): ?string | setClientId(?string clientId): void |
| `createdAt` | `?string` | Optional | - | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `creatorIp` | `?string` | Optional | - | getCreatorIp(): ?string | setCreatorIp(?string creatorIp): void |
| `creatorUa` | `?string` | Optional | - | getCreatorUa(): ?string | setCreatorUa(?string creatorUa): void |
| `generatedBy` | `?string` | Optional | - | getGeneratedBy(): ?string | setGeneratedBy(?string generatedBy): void |
| `isActive` | `?bool` | Optional | - | getIsActive(): ?bool | setIsActive(?bool isActive): void |
| `lastUsed` | `?string` | Optional | - | getLastUsed(): ?string | setLastUsed(?string lastUsed): void |
| `scopes` | `?(string[])` | Optional | - | getScopes(): ?array | setScopes(?array scopes): void |
| `token` | `?string` | Optional | - | getToken(): ?string | setToken(?string token): void |
| `tokenLabel` | `?string` | Optional | - | getTokenLabel(): ?string | setTokenLabel(?string tokenLabel): void |
| `uuid` | `?string` | Optional | - | getUuid(): ?string | setUuid(?string uuid): void |

## Example

```php
use DockerLib\Models\Builders\AccessTokenBuilder;

$accessToken = AccessTokenBuilder::init()
    ->clientId('HUB')
    ->createdAt('2021-07-20T12:00:00.000000Z')
    ->creatorIp('127.0.0.1')
    ->creatorUa('some user agent')
    ->generatedBy('manual')
    ->isActive(true)
    ->scopes(
        [
            'repo:read'
        ]
    )
    ->token('a7a5ef25-8889-43a0-8cc7-f2a94268e861')
    ->tokenLabel('My read only token')
    ->uuid('b30bbf97-506c-4ecd-aabc-842f3cb484fb')
    ->build();
```

