
# Scim Resource Type

## Structure

`ScimResourceType`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `?string` | Optional | - | getDescription(): ?string | setDescription(?string description): void |
| `endpoint` | `?string` | Optional | - | getEndpoint(): ?string | setEndpoint(?string endpoint): void |
| `id` | `?string` | Optional | - | getId(): ?string | setId(?string id): void |
| `name` | `?string` | Optional | - | getName(): ?string | setName(?string name): void |
| `schema` | `?string` | Optional | - | getSchema(): ?string | setSchema(?string schema): void |
| `schemas` | `?(string[])` | Optional | - | getSchemas(): ?array | setSchemas(?array schemas): void |

## Example

```php
use DockerLib\Models\Builders\ScimResourceTypeBuilder;

$scimResourceType = ScimResourceTypeBuilder::init()
    ->description('User')
    ->endpoint('/Users')
    ->id('User')
    ->name('User')
    ->schema('urn:ietf:params:scim:schemas:core:2.0:User')
    ->build();
```

