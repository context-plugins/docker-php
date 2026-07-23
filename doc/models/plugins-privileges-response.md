
# Plugins Privileges Response

Describes a permission the user has to accept upon installing the plugin.

## Structure

`PluginsPrivilegesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `?string` | Optional | - | getDescription(): ?string | setDescription(?string description): void |
| `name` | `?string` | Optional | - | getName(): ?string | setName(?string name): void |
| `value` | `?(string[])` | Optional | - | getValue(): ?array | setValue(?array value): void |

## Example

```php
use DockerLib\Models\Builders\PluginsPrivilegesResponseBuilder;

$pluginsPrivilegesResponse = PluginsPrivilegesResponseBuilder::init()
    ->description('Description8')
    ->name('Name8')
    ->value(
        [
            'Value8',
            'Value9',
            'Value0'
        ]
    )
    ->build();
```

