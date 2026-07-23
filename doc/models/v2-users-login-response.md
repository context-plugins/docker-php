
# V2 Users Login Response

## Structure

`V2UsersLoginResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `token` | `?string` | Optional | Created authentication token.<br><br>This token can be used in the HTTP Authorization header as a JWT to authenticate with the Docker Hub APIs. | getToken(): ?string | setToken(?string token): void |

## Example

```php
use DockerLib\Models\Builders\V2UsersLoginResponseBuilder;

$v2UsersLoginResponse = V2UsersLoginResponseBuilder::init()
    ->token('eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c')
    ->build();
```

