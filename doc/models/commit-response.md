
# Commit Response

## Structure

`CommitResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `string` | Required | The id of the newly created object. | getId(): string | setId(string id): void |

## Example

```php
use DockerLib\Models\Builders\CommitResponseBuilder;

$commitResponse = CommitResponseBuilder::init(
    'Id4'
)->build();
```

