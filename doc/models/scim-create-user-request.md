
# Scim Create User Request

## Structure

`ScimCreateUserRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | [`?ScimUserName`](../../doc/models/scim-user-name.md) | Optional | - | getName(): ?ScimUserName | setName(?ScimUserName name): void |
| `schemas` | `string[]` | Required | - | getSchemas(): array | setSchemas(array schemas): void |
| `userName` | `string` | Required | The user's email address. This must be reachable via email. | getUserName(): string | setUserName(string userName): void |

## Example

```php
use DockerLib\Models\Builders\ScimCreateUserRequestBuilder;
use DockerLib\Models\Builders\ScimUserNameBuilder;

$scimCreateUserRequest = ScimCreateUserRequestBuilder::init(
    [
        'schemas5',
        'schemas6',
        'schemas7'
    ],
    'jon.snow@docker.com'
)
    ->name(
        ScimUserNameBuilder::init()
            ->familyName('familyName8')
            ->givenName('givenName4')
            ->build()
    )
    ->build();
```

