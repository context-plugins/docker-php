
# Scim User

## Structure

`ScimUser`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `active` | `?bool` | Optional | - | getActive(): ?bool | setActive(?bool active): void |
| `displayName` | `?string` | Optional | The username in Docker. Also known as the "Docker ID". | getDisplayName(): ?string | setDisplayName(?string displayName): void |
| `emails` | [`?(ScimEmail[])`](../../doc/models/scim-email.md) | Optional | - | getEmails(): ?array | setEmails(?array emails): void |
| `groups` | [`?(ScimGroup[])`](../../doc/models/scim-group.md) | Optional | - | getGroups(): ?array | setGroups(?array groups): void |
| `id` | `?string` | Optional | The unique identifier for the user. A v4 UUID. | getId(): ?string | setId(?string id): void |
| `meta` | [`?Meta`](../../doc/models/meta.md) | Optional | - | getMeta(): ?Meta | setMeta(?Meta meta): void |
| `name` | [`?ScimUserName`](../../doc/models/scim-user-name.md) | Optional | - | getName(): ?ScimUserName | setName(?ScimUserName name): void |
| `schemas` | `?(string[])` | Optional | - | getSchemas(): ?array | setSchemas(?array schemas): void |
| `userName` | `?string` | Optional | The user's email address. This must be reachable via email. | getUserName(): ?string | setUserName(?string userName): void |

## Example

```php
use DockerLib\Models\Builders\ScimUserBuilder;
use DockerLib\Models\Builders\ScimEmailBuilder;
use DockerLib\Models\Builders\ScimGroupBuilder;

$scimUser = ScimUserBuilder::init()
    ->active(true)
    ->displayName('jonsnow')
    ->emails(
        [
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
                ->build(),
            ScimGroupBuilder::init()
                ->display('display8')
                ->value('value8')
                ->build()
        ]
    )
    ->id('d80f7c79-7730-49d8-9a41-7c42fb622d9c')
    ->userName('jon.snow@docker.com')
    ->build();
```

