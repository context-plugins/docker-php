
# Scim Schema

## Structure

`ScimSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `attributes` | [`?(ScimSchemaParentAttribute[])`](../../doc/models/scim-schema-parent-attribute.md) | Optional | - | getAttributes(): ?array | setAttributes(?array attributes): void |
| `description` | `?string` | Optional | - | getDescription(): ?string | setDescription(?string description): void |
| `id` | `?string` | Optional | - | getId(): ?string | setId(?string id): void |
| `name` | `?string` | Optional | - | getName(): ?string | setName(?string name): void |
| `schemas` | `?(string[])` | Optional | - | getSchemas(): ?array | setSchemas(?array schemas): void |

## Example

```php
use DockerLib\Models\Builders\ScimSchemaBuilder;

$scimSchema = ScimSchemaBuilder::init()
    ->attributes(
        []
    )
    ->description('User Account')
    ->id('urn:ietf:params:scim:schemas:core:2.0:User')
    ->name('User')
    ->schemas(
        [
            'urn:ietf:params:scim:schemas:core:2.0:Schema'
        ]
    )
    ->build();
```

