
# Error Detail

## Structure

`ErrorDetail`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `code` | `?int` | Optional | - | getCode(): ?int | setCode(?int code): void |
| `message` | `?string` | Optional | - | getMessage(): ?string | setMessage(?string message): void |

## Example

```php
use DockerLib\Models\Builders\ErrorDetailBuilder;

$errorDetail = ErrorDetailBuilder::init()
    ->code(118)
    ->message('message4')
    ->build();
```

