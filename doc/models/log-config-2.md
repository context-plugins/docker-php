
# Log Config 2

## Structure

`LogConfig2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `config` | `?array<string,string>` | Optional | - | getConfig(): ?array | setConfig(?array config): void |
| `type` | [`?string(Type2Enum)`](../../doc/models/type-2-enum.md) | Optional | - | getType(): ?string | setType(?string type): void |

## Example

```php
use DockerLib\Models\Builders\LogConfig2Builder;
use DockerLib\Models\Type2Enum;

$logConfig2 = LogConfig2Builder::init()
    ->config(
        [
            'key0' => 'Config0',
            'key1' => 'Config1',
            'key2' => 'Config2'
        ]
    )
    ->type(Type2Enum::SPLUNK)
    ->build();
```

