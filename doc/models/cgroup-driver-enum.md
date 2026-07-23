
# Cgroup Driver Enum

The driver to use for managing cgroups.

## Enumeration

`CgroupDriverEnum`

## Fields

| Name |
|  --- |
| `CGROUPFS` |
| `SYSTEMD` |

## Example

```php
use DockerLib\Models\CgroupDriverEnum;

$cgroupDriver = CgroupDriverEnum::CGROUPFS;
```

