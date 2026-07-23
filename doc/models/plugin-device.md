
# Plugin Device

## Structure

`PluginDevice`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `string` | Required | - | getDescription(): string | setDescription(string description): void |
| `name` | `string` | Required | - | getName(): string | setName(string name): void |
| `path` | `string` | Required | - | getPath(): string | setPath(string path): void |
| `settable` | `string[]` | Required | - | getSettable(): array | setSettable(array settable): void |

## Example

```php
use DockerLib\Models\Builders\PluginDeviceBuilder;

$pluginDevice = PluginDeviceBuilder::init(
    'Description2',
    'Name4',
    '/dev/fuse',
    [
        'Settable3',
        'Settable4'
    ]
)->build();
```

