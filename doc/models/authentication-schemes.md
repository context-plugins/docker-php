
# Authentication Schemes

## Structure

`AuthenticationSchemes`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `?string` | Optional | - | getDescription(): ?string | setDescription(?string description): void |
| `name` | `?string` | Optional | - | getName(): ?string | setName(?string name): void |
| `specUri` | `?string` | Optional | - | getSpecUri(): ?string | setSpecUri(?string specUri): void |
| `type` | `?string` | Optional | - | getType(): ?string | setType(?string type): void |

## Example

```php
use DockerLib\Models\Builders\AuthenticationSchemesBuilder;

$authenticationSchemes = AuthenticationSchemesBuilder::init()
    ->description('The OAuth 2.0 Bearer Token Authentication scheme. OAuth enables clients to access protected resources by obtaining an access token, which is defined in RFC 6750 as "a string representing an access authorization issued to the client", rather than using the resource owner\'s credentials directly.')
    ->name('OAuth 2.0 Bearer Token')
    ->specUri('http://tools.ietf.org/html/rfc6750')
    ->type('oauthbearertoken')
    ->build();
```

