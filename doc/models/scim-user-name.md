
# Scim User Name

## Structure

`ScimUserName`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `familyName` | `?string` | Optional | - | getFamilyName(): ?string | setFamilyName(?string familyName): void |
| `givenName` | `?string` | Optional | - | getGivenName(): ?string | setGivenName(?string givenName): void |

## Example

```php
use DockerLib\Models\Builders\ScimUserNameBuilder;

$scimUserName = ScimUserNameBuilder::init()
    ->familyName('Snow')
    ->givenName('Jon')
    ->build();
```

