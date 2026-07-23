
# Auth Config

## Structure

`AuthConfig`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `email` | `?string` | Optional | - | getEmail(): ?string | setEmail(?string email): void |
| `password` | `?string` | Optional | - | getPassword(): ?string | setPassword(?string password): void |
| `serveraddress` | `?string` | Optional | - | getServeraddress(): ?string | setServeraddress(?string serveraddress): void |
| `username` | `?string` | Optional | - | getUsername(): ?string | setUsername(?string username): void |

## Example

```php
use DockerLib\Models\Builders\AuthConfigBuilder;

$authConfig = AuthConfigBuilder::init()
    ->email('email8')
    ->password('xxxx')
    ->serveraddress('https://index.docker.io/v1/')
    ->username('hannibal')
    ->build();
```

