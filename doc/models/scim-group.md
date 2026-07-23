
# Scim Group

## Structure

`ScimGroup`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `display` | `?string` | Optional | - | getDisplay(): ?string | setDisplay(?string display): void |
| `value` | `?string` | Optional | - | getValue(): ?string | setValue(?string value): void |

## Example

```php
use DockerLib\Models\Builders\ScimGroupBuilder;

$scimGroup = ScimGroupBuilder::init()
    ->display('nightswatch')
    ->value('nightswatch')
    ->build();
```

