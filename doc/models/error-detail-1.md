
# Error Detail 1

Error with a detail field.

## Structure

`ErrorDetail1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `detail` | `?string` | Optional | The error message. | getDetail(): ?string | setDetail(?string detail): void |

## Example

```php
use DockerLib\Models\Builders\ErrorDetail1Builder;

$errorDetail1 = ErrorDetail1Builder::init()
    ->detail('detail4')
    ->build();
```

