
# M Interface

The interface between Docker and the plugin

## Structure

`MInterface`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `socket` | `string` | Required | - | getSocket(): string | setSocket(string socket): void |
| `types` | [`PluginInterfaceType[]`](../../doc/models/plugin-interface-type.md) | Required | - | getTypes(): array | setTypes(array types): void |

## Example

```php
use DockerLib\Models\Builders\MInterfaceBuilder;
use DockerLib\Models\Builders\PluginInterfaceTypeBuilder;

$interface = MInterfaceBuilder::init(
    'plugins.sock',
    [
        PluginInterfaceTypeBuilder::init(
            'Capability4',
            'Prefix0',
            'Version8'
        )->build()
    ]
)->build();
```

