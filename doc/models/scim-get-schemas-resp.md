
# Scim Get Schemas Resp

## Structure

`ScimGetSchemasResp`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `resources` | [`?(ScimSchema[])`](../../doc/models/scim-schema.md) | Optional | - | getResources(): ?array | setResources(?array resources): void |
| `schemas` | `?(string[])` | Optional | - | getSchemas(): ?array | setSchemas(?array schemas): void |
| `totalResults` | `?int` | Optional | - | getTotalResults(): ?int | setTotalResults(?int totalResults): void |

## Example

```php
use DockerLib\Models\Builders\ScimGetSchemasRespBuilder;
use DockerLib\Models\Builders\ScimSchemaBuilder;
use DockerLib\Models\Builders\ScimSchemaParentAttributeBuilder;

$scimGetSchemasResp = ScimGetSchemasRespBuilder::init()
    ->resources(
        [
            ScimSchemaBuilder::init()
                ->attributes(
                    [
                        null,
                        ScimSchemaParentAttributeBuilder::init()->build()
                    ]
                )
                ->description('description0')
                ->id('id0')
                ->name('name0')
                ->schemas(
                    [
                        'schemas1',
                        'schemas0',
                        'schemas9'
                    ]
                )
                ->build(),
            ScimSchemaBuilder::init()
                ->attributes(
                    [
                        null,
                        ScimSchemaParentAttributeBuilder::init()->build()
                    ]
                )
                ->description('description0')
                ->id('id0')
                ->name('name0')
                ->schemas(
                    [
                        'schemas1',
                        'schemas0',
                        'schemas9'
                    ]
                )
                ->build(),
            ScimSchemaBuilder::init()
                ->attributes(
                    [
                        null,
                        ScimSchemaParentAttributeBuilder::init()->build()
                    ]
                )
                ->description('description0')
                ->id('id0')
                ->name('name0')
                ->schemas(
                    [
                        'schemas1',
                        'schemas0',
                        'schemas9'
                    ]
                )
                ->build()
        ]
    )
    ->schemas(
        [
            'urn:ietf:params:scim:api:messages:2.0:ListResponse'
        ]
    )
    ->totalResults(1)
    ->build();
```

