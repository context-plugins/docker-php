
# Plugin Spec 2

## Structure

`PluginSpec2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `disabled` | `?bool` | Optional | Disable the plugin once scheduled. | getDisabled(): ?bool | setDisabled(?bool disabled): void |
| `name` | `?string` | Optional | The name or 'alias' to use for the plugin. | getName(): ?string | setName(?string name): void |
| `pluginPrivilege` | [`?(PluginPrivilege[])`](../../doc/models/plugin-privilege.md) | Optional | - | getPluginPrivilege(): ?array | setPluginPrivilege(?array pluginPrivilege): void |
| `remote` | `?string` | Optional | The plugin image reference to use. | getRemote(): ?string | setRemote(?string remote): void |

## Example

```php
use DockerLib\Models\Builders\PluginSpec2Builder;
use DockerLib\Models\Builders\PluginPrivilegeBuilder;

$pluginSpec2 = PluginSpec2Builder::init()
    ->disabled(false)
    ->name('Name0')
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
    ->remote('Remote6')
    ->build();
```

