
# Type 2 Enum

## Enumeration

`Type2Enum`

## Fields

| Name |
|  --- |
| `JSONFILE` |
| `SYSLOG` |
| `JOURNALD` |
| `GELF` |
| `FLUENTD` |
| `AWSLOGS` |
| `SPLUNK` |
| `ETWLOGS` |
| `NONE` |

## Example

```php
use DockerLib\Models\Type2Enum;

$type2 = Type2Enum::AWSLOGS;
```

