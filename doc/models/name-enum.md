
# Name Enum

- Empty string means not to restart
- `always` Always restart
- `unless-stopped` Restart always except when the user has manually stopped the container
- `on-failure` Restart only when the container exit code is non-zero

## Enumeration

`NameEnum`

## Fields

| Name |
|  --- |
| `ALWAYS` |
| `UNLESSSTOPPED` |
| `ONFAILURE` |

## Example

```php
use DockerLib\Models\NameEnum;

$name = NameEnum::ONFAILURE;
```

