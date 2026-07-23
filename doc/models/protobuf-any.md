
# Protobuf Any

## Structure

`ProtobufAny`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `typeUrl` | `?string` | Optional | - | getTypeUrl(): ?string | setTypeUrl(?string typeUrl): void |
| `value` | `?string` | Optional | - | getValue(): ?string | setValue(?string value): void |

## Example

```php
use DockerLib\Models\Builders\ProtobufAnyBuilder;

$protobufAny = ProtobufAnyBuilder::init()
    ->typeUrl('type_url0')
    ->value('value8')
    ->build();
```

