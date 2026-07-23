
# Plugin Privilege

Describes a permission accepted by the user upon installing the plugin.

## Structure

`PluginPrivilege`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `?string` | Optional | - | getDescription(): ?string | setDescription(?string description): void |
| `name` | `?string` | Optional | - | getName(): ?string | setName(?string name): void |
| `value` | `?(string[])` | Optional | - | getValue(): ?array | setValue(?array value): void |

## Example

```php
use DockerLib\Models\Builders\PluginPrivilegeBuilder;

$pluginPrivilege = PluginPrivilegeBuilder::init()
    ->description('Description8')
    ->name('Name8')
    ->value(
        [
            'Value8',
            'Value9'
        ]
    )
    ->build();
```

