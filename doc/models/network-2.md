
# Network 2

## Structure

`Network2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `aliases` | `?(string[])` | Optional | - | getAliases(): ?array | setAliases(?array aliases): void |
| `target` | `?string` | Optional | - | getTarget(): ?string | setTarget(?string target): void |

## Example

```php
use DockerLib\Models\Builders\Network2Builder;

$network2 = Network2Builder::init()
    ->aliases(
        [
            'Aliases8',
            'Aliases7'
        ]
    )
    ->target('Target0')
    ->build();
```

