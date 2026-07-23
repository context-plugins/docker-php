
# Containers Archive Response

## Structure

`ContainersArchiveResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `message` | `string` | Required | - | getMessage(): string | setMessage(string message): void |

## Example

```php
use DockerLib\Models\Builders\ContainersArchiveResponseBuilder;

$containersArchiveResponse = ContainersArchiveResponseBuilder::init(
    'No such container: c2ada9df5af8'
)->build();
```

