
# Users 2 FA Login Request

Second factor user login details

## Structure

`Users2FALoginRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `code` | `string` | Required | The Time-based One-Time Password of the Docker Hub account to authenticate with. | getCode(): string | setCode(string code): void |
| `login2faToken` | `string` | Required | The intermediate 2FA token returned from `/v2/users/login` API. | getLogin2faToken(): string | setLogin2faToken(string login2faToken): void |

## Example

```php
use DockerLib\Models\Builders\Users2FALoginRequestBuilder;

$users2FALoginRequest = Users2FALoginRequestBuilder::init(
    '123456',
    'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c'
)->build();
```

