
# Scim Service Provider Config

## Structure

`ScimServiceProviderConfig`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `authenticationSchemes` | [`?AuthenticationSchemes`](../../doc/models/authentication-schemes.md) | Optional | - | getAuthenticationSchemes(): ?AuthenticationSchemes | setAuthenticationSchemes(?AuthenticationSchemes authenticationSchemes): void |
| `bulk` | [`?Bulk`](../../doc/models/bulk.md) | Optional | - | getBulk(): ?Bulk | setBulk(?Bulk bulk): void |
| `changePassword` | [`?ChangePassword`](../../doc/models/change-password.md) | Optional | - | getChangePassword(): ?ChangePassword | setChangePassword(?ChangePassword changePassword): void |
| `documentationUri` | `?string` | Optional | - | getDocumentationUri(): ?string | setDocumentationUri(?string documentationUri): void |
| `etag` | [`?Etag`](../../doc/models/etag.md) | Optional | - | getEtag(): ?Etag | setEtag(?Etag etag): void |
| `filter` | [`?Filter`](../../doc/models/filter.md) | Optional | - | getFilter(): ?Filter | setFilter(?Filter filter): void |
| `patch` | [`?Patch`](../../doc/models/patch.md) | Optional | - | getPatch(): ?Patch | setPatch(?Patch patch): void |
| `schemas` | `?(string[])` | Optional | - | getSchemas(): ?array | setSchemas(?array schemas): void |
| `sort` | [`?Sort`](../../doc/models/sort.md) | Optional | - | getSort(): ?Sort | setSort(?Sort sort): void |

## Example

```php
use DockerLib\Models\Builders\ScimServiceProviderConfigBuilder;
use DockerLib\Models\Builders\AuthenticationSchemesBuilder;
use DockerLib\Models\Builders\BulkBuilder;
use DockerLib\Models\Builders\ChangePasswordBuilder;
use DockerLib\Models\Builders\EtagBuilder;

$scimServiceProviderConfig = ScimServiceProviderConfigBuilder::init()
    ->authenticationSchemes(
        AuthenticationSchemesBuilder::init()
            ->description('description0')
            ->name('name0')
            ->specUri('specUri4')
            ->type('type0')
            ->build()
    )
    ->bulk(
        BulkBuilder::init()
            ->maxOperations(148)
            ->maxPayloadSize(104)
            ->supported(false)
            ->build()
    )
    ->changePassword(
        ChangePasswordBuilder::init()
            ->supported(false)
            ->build()
    )
    ->documentationUri('documentationUri8')
    ->etag(
        EtagBuilder::init()
            ->supported(false)
            ->build()
    )
    ->schemas(
        [
            'urn:ietf:params:scim:schemas:core:2.0:ServiceProviderConfig'
        ]
    )
    ->build();
```

