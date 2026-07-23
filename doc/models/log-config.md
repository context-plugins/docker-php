
# Log Config

The logging configuration for this container

## Structure

`LogConfig`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `config` | `?array<string,string>` | Optional | - | getConfig(): ?array | setConfig(?array config): void |
| `type` | [`?string(Type2Enum)`](../../doc/models/type-2-enum.md) | Optional | - | getType(): ?string | setType(?string type): void |

## Example

```php
use DockerLib\Models\Builders\LogConfigBuilder;
use DockerLib\Models\Type2Enum;

$logConfig = LogConfigBuilder::init()
    ->config(
        [
            'key0' => 'Config6',
            'key1' => 'Config7',
            'key2' => 'Config8'
        ]
    )
    ->type(Type2Enum::SPLUNK)
    ->build();
```

