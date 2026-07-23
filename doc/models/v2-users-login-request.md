
# V2 Users Login Request

## Structure

`V2UsersLoginRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `password` | `string` | Required | The password or personal access token (PAT) of the Docker Hub account to authenticate with. | getPassword(): string | setPassword(string password): void |
| `username` | `string` | Required | The username of the Docker Hub account to authenticate with. | getUsername(): string | setUsername(string username): void |

## Example

```php
use DockerLib\Models\Builders\V2UsersLoginRequestBuilder;

$v2UsersLoginRequest = V2UsersLoginRequestBuilder::init(
    'hunter2',
    'myusername'
)->build();
```

