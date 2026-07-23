
# Plugin Pull Body

Describes a permission accepted by the user upon installing the plugin.

## Structure

`PluginPullBody`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `?string` | Optional | - | getDescription(): ?string | setDescription(?string description): void |
| `name` | `?string` | Optional | - | getName(): ?string | setName(?string name): void |
| `value` | `?(string[])` | Optional | - | getValue(): ?array | setValue(?array value): void |

## Example

```php
use DockerLib\Models\Builders\PluginPullBodyBuilder;

$pluginPullBody = PluginPullBodyBuilder::init()
    ->description('Description0')
    ->name('Name6')
    ->value(
        [
            'Value0'
        ]
    )
    ->build();
```

