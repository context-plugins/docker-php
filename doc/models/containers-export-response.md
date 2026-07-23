
# Containers Export Response

## Structure

`ContainersExportResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `message` | `string` | Required | - | getMessage(): string | setMessage(string message): void |

## Example

```php
use DockerLib\Models\Builders\ContainersExportResponseBuilder;

$containersExportResponse = ContainersExportResponseBuilder::init(
    'No such container: c2ada9df5af8'
)->build();
```

