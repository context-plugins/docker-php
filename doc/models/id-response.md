
# Id Response

Response to an API call that returns just an Id

## Structure

`IdResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `string` | Required | The id of the newly created object. | getId(): string | setId(string id): void |

## Example

```php
use DockerLib\Models\Builders\IdResponseBuilder;

$idResponse = IdResponseBuilder::init(
    'Id6'
)->build();
```

