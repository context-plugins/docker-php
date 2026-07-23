
# Scim Get Resource Types Resp

## Structure

`ScimGetResourceTypesResp`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `resources` | [`?(ScimResourceType[])`](../../doc/models/scim-resource-type.md) | Optional | - | getResources(): ?array | setResources(?array resources): void |
| `schemas` | `?(string[])` | Optional | - | getSchemas(): ?array | setSchemas(?array schemas): void |
| `totalResults` | `?int` | Optional | - | getTotalResults(): ?int | setTotalResults(?int totalResults): void |

## Example

```php
use DockerLib\Models\Builders\ScimGetResourceTypesRespBuilder;
use DockerLib\Models\Builders\ScimResourceTypeBuilder;

$scimGetResourceTypesResp = ScimGetResourceTypesRespBuilder::init()
    ->resources(
        [
            ScimResourceTypeBuilder::init()
                ->description('description0')
                ->endpoint('endpoint8')
                ->id('id0')
                ->name('name0')
                ->schema('schema2')
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

