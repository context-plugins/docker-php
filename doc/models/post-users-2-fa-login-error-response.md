
# Post Users 2 FA Login Error Response

failed second factor login response.

## Structure

`PostUsers2FALoginErrorResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `detail` | `?string` | Optional | Description of the error. | getDetail(): ?string | setDetail(?string detail): void |

## Example

```php
use DockerLib\Models\Builders\PostUsers2FALoginErrorResponseBuilder;

$postUsers2FALoginErrorResponse = PostUsers2FALoginErrorResponseBuilder::init()
    ->detail('Incorrect authentication credentials')
    ->build();
```

