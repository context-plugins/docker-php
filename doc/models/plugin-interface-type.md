
# Plugin Interface Type

## Structure

`PluginInterfaceType`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `capability` | `string` | Required | - | getCapability(): string | setCapability(string capability): void |
| `prefix` | `string` | Required | - | getPrefix(): string | setPrefix(string prefix): void |
| `version` | `string` | Required | - | getVersion(): string | setVersion(string version): void |

## Example

```php
use DockerLib\Models\Builders\PluginInterfaceTypeBuilder;

$pluginInterfaceType = PluginInterfaceTypeBuilder::init(
    'Capability0',
    'Prefix4',
    'Version6'
)->build();
```

