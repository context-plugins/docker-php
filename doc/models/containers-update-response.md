
# Containers Update Response

## Structure

`ContainersUpdateResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `warnings` | `?(string[])` | Optional | - | getWarnings(): ?array | setWarnings(?array warnings): void |

## Example

```php
use DockerLib\Models\Builders\ContainersUpdateResponseBuilder;

$containersUpdateResponse = ContainersUpdateResponseBuilder::init()
    ->warnings(
        [
            'Warnings7',
            'Warnings8'
        ]
    )
    ->build();
```

