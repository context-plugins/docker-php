
# Error Response

Represents an error.

## Structure

`ErrorResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `message` | `string` | Required | The error message. | getMessage(): string | setMessage(string message): void |

## Example

```php
use DockerLib\Models\Builders\ErrorResponseBuilder;

$errorResponse = ErrorResponseBuilder::init(
    'Something went wrong.'
)->build();
```

