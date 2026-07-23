
# Scim Get Users Resp

## Structure

`ScimGetUsersResp`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `itemsPerPage` | `?int` | Optional | - | getItemsPerPage(): ?int | setItemsPerPage(?int itemsPerPage): void |
| `resources` | [`?(ScimUser[])`](../../doc/models/scim-user.md) | Optional | - | getResources(): ?array | setResources(?array resources): void |
| `schemas` | `?(string[])` | Optional | - | getSchemas(): ?array | setSchemas(?array schemas): void |
| `startIndex` | `?int` | Optional | - | getStartIndex(): ?int | setStartIndex(?int startIndex): void |
| `totalResults` | `?int` | Optional | - | getTotalResults(): ?int | setTotalResults(?int totalResults): void |

## Example

```php
use DockerLib\Models\Builders\ScimGetUsersRespBuilder;
use DockerLib\Models\Builders\ScimUserBuilder;
use DockerLib\Models\Builders\ScimEmailBuilder;
use DockerLib\Models\Builders\ScimGroupBuilder;

$scimGetUsersResp = ScimGetUsersRespBuilder::init()
    ->itemsPerPage(10)
    ->resources(
        [
            ScimUserBuilder::init()
                ->active(false)
                ->displayName('displayName2')
                ->emails(
                    [
                        ScimEmailBuilder::init()
                            ->display('display8')
                            ->primary(false)
                            ->value('value8')
                            ->build(),
                        ScimEmailBuilder::init()
                            ->display('display8')
                            ->primary(false)
                            ->value('value8')
                            ->build(),
                        ScimEmailBuilder::init()
                            ->display('display8')
                            ->primary(false)
                            ->value('value8')
                            ->build()
                    ]
                )
                ->groups(
                    [
                        ScimGroupBuilder::init()
                            ->display('display8')
                            ->value('value8')
                            ->build()
                    ]
                )
                ->id('id0')
                ->build(),
            ScimUserBuilder::init()
                ->active(false)
                ->displayName('displayName2')
                ->emails(
                    [
                        ScimEmailBuilder::init()
                            ->display('display8')
                            ->primary(false)
                            ->value('value8')
                            ->build(),
                        ScimEmailBuilder::init()
                            ->display('display8')
                            ->primary(false)
                            ->value('value8')
                            ->build(),
                        ScimEmailBuilder::init()
                            ->display('display8')
                            ->primary(false)
                            ->value('value8')
                            ->build()
                    ]
                )
                ->groups(
                    [
                        ScimGroupBuilder::init()
                            ->display('display8')
                            ->value('value8')
                            ->build()
                    ]
                )
                ->id('id0')
                ->build(),
            ScimUserBuilder::init()
                ->active(false)
                ->displayName('displayName2')
                ->emails(
                    [
                        ScimEmailBuilder::init()
                            ->display('display8')
                            ->primary(false)
                            ->value('value8')
                            ->build(),
                        ScimEmailBuilder::init()
                            ->display('display8')
                            ->primary(false)
                            ->value('value8')
                            ->build(),
                        ScimEmailBuilder::init()
                            ->display('display8')
                            ->primary(false)
                            ->value('value8')
                            ->build()
                    ]
                )
                ->groups(
                    [
                        ScimGroupBuilder::init()
                            ->display('display8')
                            ->value('value8')
                            ->build()
                    ]
                )
                ->id('id0')
                ->build()
        ]
    )
    ->schemas(
        [
            'urn:ietf:params:scim:api:messages:2.0:ListResponse'
        ]
    )
    ->startIndex(1)
    ->totalResults(1)
    ->build();
```

