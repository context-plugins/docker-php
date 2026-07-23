
# V2 Users 2 Fa Login Response

## Structure

`V2Users2faLoginResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `token` | `?string` | Optional | Created authentication token.<br><br>This token can be used in the HTTP Authorization header as a JWT to authenticate with the Docker Hub APIs. | getToken(): ?string | setToken(?string token): void |

## Example

```php
use DockerLib\Models\Builders\V2Users2faLoginResponseBuilder;

$v2Users2faLoginResponse = V2Users2faLoginResponseBuilder::init()
    ->token('eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c')
    ->build();
```

