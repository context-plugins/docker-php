
# Plugin Env

## Structure

`PluginEnv`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `string` | Required | - | getDescription(): string | setDescription(string description): void |
| `name` | `string` | Required | - | getName(): string | setName(string name): void |
| `settable` | `string[]` | Required | - | getSettable(): array | setSettable(array settable): void |
| `value` | `string` | Required | - | getValue(): string | setValue(string value): void |

## Example

```php
use DockerLib\Models\Builders\PluginEnvBuilder;

$pluginEnv = PluginEnvBuilder::init(
    'Description0',
    'Name6',
    [
        'Settable5'
    ],
    'Value6'
)->build();
```

