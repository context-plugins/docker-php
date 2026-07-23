
# Get Audit Logs Response

GetAuditLogs response.

## Structure

`GetAuditLogsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `logs` | [`?(AuditLog[])`](../../doc/models/audit-log.md) | Optional | List of audit log events. | getLogs(): ?array | setLogs(?array logs): void |

## Example

```php
use DockerLib\Models\Builders\GetAuditLogsResponseBuilder;
use DockerLib\Models\Builders\AuditLogBuilder;

$getAuditLogsResponse = GetAuditLogsResponseBuilder::init()
    ->logs(
        [
            AuditLogBuilder::init()
                ->account('account8')
                ->action('action4')
                ->actionDescription('action_description2')
                ->actor('actor8')
                ->data(
                    [
                        'key0' => 'data3',
                        'key1' => 'data4',
                        'key2' => 'data5'
                    ]
                )
                ->build(),
            AuditLogBuilder::init()
                ->account('account8')
                ->action('action4')
                ->actionDescription('action_description2')
                ->actor('actor8')
                ->data(
                    [
                        'key0' => 'data3',
                        'key1' => 'data4',
                        'key2' => 'data5'
                    ]
                )
                ->build()
        ]
    )
    ->build();
```

