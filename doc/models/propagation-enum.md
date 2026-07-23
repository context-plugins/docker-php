
# Propagation Enum

A propagation mode with the value `[r]private`, `[r]shared`, or `[r]slave`.

## Enumeration

`PropagationEnum`

## Fields

| Name |
|  --- |
| `PRIVATE_` |
| `RPRIVATE` |
| `SHARED` |
| `RSHARED` |
| `SLAVE` |
| `RSLAVE` |

## Example

```php
use DockerLib\Models\PropagationEnum;

$propagation = PropagationEnum::SLAVE;
```

