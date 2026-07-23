
# Containers Create Response

## Structure

`ContainersCreateResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `string` | Required | The ID of the created container | getId(): string | setId(string id): void |
| `warnings` | `string[]` | Required | Warnings encountered when creating the container | getWarnings(): array | setWarnings(array warnings): void |

## Example

```php
use DockerLib\Models\Builders\ContainersCreateResponseBuilder;

$containersCreateResponse = ContainersCreateResponseBuilder::init(
    'Id6',
    [
        'Warnings1',
        'Warnings2'
    ]
)->build();
```

