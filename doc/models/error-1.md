
# Error 1

## Structure

`Error1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `digest` | `?string` | Optional | Digest of the image that caused the error. | getDigest(): ?string | setDigest(?string digest): void |
| `error` | [`?string(Error2Enum)`](../../doc/models/error-2-enum.md) | Optional | - | getError(): ?string | setError(?string error): void |
| `repository` | `?string` | Optional | Name of the repository of the image that caused the error. | getRepository(): ?string | setRepository(?string repository): void |

## Example

```php
use DockerLib\Models\Builders\Error1Builder;
use DockerLib\Models\Error2Enum;

$error1 = Error1Builder::init()
    ->digest('sha256:1234567890abcdefghijklmnopqrstuvwxyz1234567890abcdefghijklmnopqr')
    ->error(Error2Enum::NOT_FOUND)
    ->repository('myrepo')
    ->build();
```

