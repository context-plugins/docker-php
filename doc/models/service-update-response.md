
# Service Update Response

## Structure

`ServiceUpdateResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `warnings` | `?(string[])` | Optional | Optional warning messages | getWarnings(): ?array | setWarnings(?array warnings): void |

## Example

```php
use DockerLib\Models\Builders\ServiceUpdateResponseBuilder;

$serviceUpdateResponse = ServiceUpdateResponseBuilder::init()
    ->warnings(
        [
            'Warnings7',
            'Warnings8',
            'Warnings9'
        ]
    )
    ->build();
```

