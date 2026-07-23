
# Auth Response

## Structure

`AuthResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `identityToken` | `?string` | Optional | An opaque token used to authenticate a user after a successful login | getIdentityToken(): ?string | setIdentityToken(?string identityToken): void |
| `status` | `string` | Required | The status of the authentication | getStatus(): string | setStatus(string status): void |

## Example

```php
use DockerLib\Models\Builders\AuthResponseBuilder;

$authResponse = AuthResponseBuilder::init(
    'Status2'
)
    ->identityToken('IdentityToken4')
    ->build();
```

