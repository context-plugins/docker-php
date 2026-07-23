
# Scope Enum

The level at which the volume exists. Either `global` for cluster-wide, or `local` for machine level.

## Enumeration

`ScopeEnum`

## Fields

| Name |
|  --- |
| `LOCAL` |
| `GLOBAL_` |

## Example

```php
use DockerLib\Models\ScopeEnum;

$scope = ScopeEnum::LOCAL;
```

