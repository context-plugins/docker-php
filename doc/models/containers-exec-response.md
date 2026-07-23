
# Containers Exec Response

## Structure

`ContainersExecResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `string` | Required | The id of the newly created object. | getId(): string | setId(string id): void |

## Example

```php
use DockerLib\Models\Builders\ContainersExecResponseBuilder;

$containersExecResponse = ContainersExecResponseBuilder::init(
    'Id2'
)->build();
```

