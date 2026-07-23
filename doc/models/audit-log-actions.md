
# Audit Log Actions

## Structure

`AuditLogActions`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `actions` | [`?(AuditLogAction[])`](../../doc/models/audit-log-action.md) | Optional | List of audit log actions. | getActions(): ?array | setActions(?array actions): void |
| `label` | `?string` | Optional | Grouping label for a particular set of audit log actions. | getLabel(): ?string | setLabel(?string label): void |

## Example

```php
use DockerLib\Models\Builders\AuditLogActionsBuilder;
use DockerLib\Models\Builders\AuditLogActionBuilder;

$auditLogActions = AuditLogActionsBuilder::init()
    ->actions(
        [
            AuditLogActionBuilder::init()
                ->description('description8')
                ->label('label8')
                ->name('name8')
                ->build()
        ]
    )
    ->label('label0')
    ->build();
```

