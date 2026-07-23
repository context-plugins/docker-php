
# Isolation 1 Enum

Represents the isolation technology to use as a default for containers.
The supported values are platform-specific.

If no isolation value is specified on daemon start, on Windows client,
the default is `hyperv`, and on Windows server, the default is `process`.

This option is currently not used on other platforms.

## Enumeration

`Isolation1Enum`

## Fields

| Name |
|  --- |
| `DEFAULT_` |
| `HYPERV` |
| `PROCESS` |

## Example

```php
use DockerLib\Models\Isolation1Enum;

$isolation1 = Isolation1Enum::HYPERV;
```

