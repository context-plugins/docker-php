
# Plugin Spec

Invalid when specified with `ContainerSpec`. *(Experimental release only.)*

## Structure

`PluginSpec`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `disabled` | `?bool` | Optional | Disable the plugin once scheduled. | getDisabled(): ?bool | setDisabled(?bool disabled): void |
| `name` | `?string` | Optional | The name or 'alias' to use for the plugin. | getName(): ?string | setName(?string name): void |
| `pluginPrivilege` | [`?(PluginPrivilege[])`](../../doc/models/plugin-privilege.md) | Optional | - | getPluginPrivilege(): ?array | setPluginPrivilege(?array pluginPrivilege): void |
| `remote` | `?string` | Optional | The plugin image reference to use. | getRemote(): ?string | setRemote(?string remote): void |

## Example

```php
use DockerLib\Models\Builders\PluginSpecBuilder;
use DockerLib\Models\Builders\PluginPrivilegeBuilder;

$pluginSpec = PluginSpecBuilder::init()
    ->disabled(false)
    ->name('Name2')
    ->pluginPrivilege(
        [
            PluginPrivilegeBuilder::init()
                ->description('Description0')
                ->name('Name6')
                ->value(
                    [
                        'Value0',
                        'Value1'
                    ]
                )
                ->build(),
            PluginPrivilegeBuilder::init()
                ->description('Description0')
                ->name('Name6')
                ->value(
                    [
                        'Value0',
                        'Value1'
                    ]
                )
                ->build()
        ]
    )
    ->remote('Remote8')
    ->build();
```

