
# Plugin 2

## Structure

`Plugin2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | - | getName(): ?string | setName(?string name): void |
| `type` | `?string` | Optional | - | getType(): ?string | setType(?string type): void |

## Example

```php
use DockerLib\Models\Builders\Plugin2Builder;

$plugin2 = Plugin2Builder::init()
    ->name('Name6')
    ->type('Type6')
    ->build();
```

