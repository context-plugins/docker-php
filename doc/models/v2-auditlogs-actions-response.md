
# V2 Auditlogs Actions Response

## Structure

`V2AuditlogsActionsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `actions` | [`?array<string,AuditLogActions>`](../../doc/models/audit-log-actions.md) | Optional | Map of audit log actions. | getActions(): ?array | setActions(?array actions): void |

## Example

```php
use DockerLib\Models\Builders\V2AuditlogsActionsResponseBuilder;
use DockerLib\Models\Builders\AuditLogActionsBuilder;
use DockerLib\Models\Builders\AuditLogActionBuilder;

$v2AuditlogsActionsResponse = V2AuditlogsActionsResponseBuilder::init()
    ->actions(
        [
            'key0' => AuditLogActionsBuilder::init()
                ->actions(
                    [
                        AuditLogActionBuilder::init()
                            ->description('description8')
                            ->label('label8')
                            ->name('name8')
                            ->build()
                    ]
                )
                ->label('label8')
                ->build()
        ]
    )
    ->build();
```

