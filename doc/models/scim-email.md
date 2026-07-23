
# Scim Email

## Structure

`ScimEmail`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `display` | `?string` | Optional | - | getDisplay(): ?string | setDisplay(?string display): void |
| `primary` | `?bool` | Optional | - | getPrimary(): ?bool | setPrimary(?bool primary): void |
| `value` | `?string` | Optional | - | getValue(): ?string | setValue(?string value): void |

## Example

```php
use DockerLib\Models\Builders\ScimEmailBuilder;

$scimEmail = ScimEmailBuilder::init()
    ->display('jon.snow@docker.com')
    ->primary(true)
    ->value('jon.snow@docker.com')
    ->build();
```

