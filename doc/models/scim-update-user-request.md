
# Scim Update User Request

## Structure

`ScimUpdateUserRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `enabled` | `?bool` | Optional | If this is omitted from the request, it will default to false resulting in a deactivated user.<br><br>**Default**: `false` | getEnabled(): ?bool | setEnabled(?bool enabled): void |
| `name` | [`?ScimUserName`](../../doc/models/scim-user-name.md) | Optional | - | getName(): ?ScimUserName | setName(?ScimUserName name): void |
| `schemas` | `string[]` | Required | - | getSchemas(): array | setSchemas(array schemas): void |

## Example

```php
use DockerLib\Models\Builders\ScimUpdateUserRequestBuilder;
use DockerLib\Models\Builders\ScimUserNameBuilder;

$scimUpdateUserRequest = ScimUpdateUserRequestBuilder::init(
    [
        'schemas5'
    ]
)
    ->enabled(false)
    ->name(
        ScimUserNameBuilder::init()
            ->familyName('familyName8')
            ->givenName('givenName4')
            ->build()
    )
    ->build();
```

