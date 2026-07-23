
# Containers Resize Response

## Structure

`ContainersResizeResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `message` | `string` | Required | - | getMessage(): string | setMessage(string message): void |

## Example

```php
use DockerLib\Models\Builders\ContainersResizeResponseBuilder;

$containersResizeResponse = ContainersResizeResponseBuilder::init(
    'No such container: c2ada9df5af8'
)->build();
```

