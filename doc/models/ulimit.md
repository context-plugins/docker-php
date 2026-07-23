
# Ulimit

## Structure

`Ulimit`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `hard` | `?int` | Optional | Hard limit | getHard(): ?int | setHard(?int hard): void |
| `name` | `?string` | Optional | Name of ulimit | getName(): ?string | setName(?string name): void |
| `soft` | `?int` | Optional | Soft limit | getSoft(): ?int | setSoft(?int soft): void |

## Example

```php
use DockerLib\Models\Builders\UlimitBuilder;

$ulimit = UlimitBuilder::init()
    ->hard(16)
    ->name('Name8')
    ->soft(116)
    ->build();
```

