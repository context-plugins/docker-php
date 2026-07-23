
# Progress Detail

## Structure

`ProgressDetail`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `code` | `?int` | Optional | - | getCode(): ?int | setCode(?int code): void |
| `message` | `?int` | Optional | - | getMessage(): ?int | setMessage(?int message): void |

## Example

```php
use DockerLib\Models\Builders\ProgressDetailBuilder;

$progressDetail = ProgressDetailBuilder::init()
    ->code(114)
    ->message(224)
    ->build();
```

