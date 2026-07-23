
# Post Users Login Error Response

failed user login response or second factor required

## Structure

`PostUsersLoginErrorResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `detail` | `string` | Required | Description of the error. | getDetail(): string | setDetail(string detail): void |
| `login2faToken` | `?string` | Optional | Short time lived token to be used on `/v2/users/2fa-login` to complete the authentication. This field is present only if 2FA is enabled. | getLogin2faToken(): ?string | setLogin2faToken(?string login2faToken): void |

## Example

```php
use DockerLib\Models\Builders\PostUsersLoginErrorResponseBuilder;

$postUsersLoginErrorResponse = PostUsersLoginErrorResponseBuilder::init(
    'Incorrect authentication credentials'
)
    ->login2faToken('eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c')
    ->build();
```

