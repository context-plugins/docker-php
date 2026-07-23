
# Plugin Mount

## Structure

`PluginMount`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `string` | Required | - | getDescription(): string | setDescription(string description): void |
| `destination` | `string` | Required | - | getDestination(): string | setDestination(string destination): void |
| `name` | `string` | Required | - | getName(): string | setName(string name): void |
| `options` | `string[]` | Required | - | getOptions(): array | setOptions(array options): void |
| `settable` | `string[]` | Required | - | getSettable(): array | setSettable(array settable): void |
| `source` | `string` | Required | - | getSource(): string | setSource(string source): void |
| `type` | `string` | Required | - | getType(): string | setType(string type): void |

## Example

```php
use DockerLib\Models\Builders\PluginMountBuilder;

$pluginMount = PluginMountBuilder::init(
    'This is a mount that\'s used by the plugin.',
    '/mnt/state',
    'some-mount',
    [
        'rbind',
        'rw'
    ],
    [
        'Settable1',
        'Settable2',
        'Settable3'
    ],
    '/var/lib/docker/plugins/',
    'bind'
)->build();
```

