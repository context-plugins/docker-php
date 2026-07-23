
# Type Enum

The mount type. Available types:

- `bind` Mounts a file or directory from the host into the container. Must exist prior to creating the container.
- `volume` Creates a volume with the given name and options (or uses a pre-existing volume with the same name and options). These are **not** removed when the container is removed.
- `tmpfs` Create a tmpfs with the given options. The mount source cannot be specified for tmpfs.

## Enumeration

`TypeEnum`

## Fields

| Name |
|  --- |
| `BIND` |
| `VOLUME` |
| `TMPFS` |

## Example

```php
use DockerLib\Models\TypeEnum;

$type = TypeEnum::TMPFS;
```

