
# Log Driver 1

Specifies the log driver to use for tasks created from this spec. If not present, the default one for the swarm will be used, finally falling back to the engine default if not specified.

## Structure

`LogDriver1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | - | getName(): ?string | setName(?string name): void |
| `options` | `?array<string,string>` | Optional | - | getOptions(): ?array | setOptions(?array options): void |

## Example

```php
use DockerLib\Models\Builders\LogDriver1Builder;

$logDriver1 = LogDriver1Builder::init()
    ->name('Name4')
    ->options(
        [
            'key0' => 'Options4',
            'key1' => 'Options3',
            'key2' => 'Options2'
        ]
    )
    ->build();
```

