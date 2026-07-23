
# Value Error

Used to error if input validation fails.

## Structure

`ValueError`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `fields` | `?(string[])` | Optional | - | getFields(): ?array | setFields(?array fields): void |
| `text` | `?string` | Optional | - | getText(): ?string | setText(?string text): void |

## Example

```php
use DockerLib\Models\Builders\ValueErrorBuilder;

$valueError = ValueErrorBuilder::init()
    ->fields(
        [
            'fields0'
        ]
    )
    ->text('text2')
    ->build();
```

