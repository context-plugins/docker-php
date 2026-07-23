
# Audit Log Action

Audit Log action

## Structure

`AuditLogAction`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `?string` | Optional | Description of audit log action. | getDescription(): ?string | setDescription(?string description): void |
| `label` | `?string` | Optional | Label for audit log action. | getLabel(): ?string | setLabel(?string label): void |
| `name` | `?string` | Optional | Name of audit log action. | getName(): ?string | setName(?string name): void |

## Example

```php
use DockerLib\Models\Builders\AuditLogActionBuilder;

$auditLogAction = AuditLogActionBuilder::init()
    ->description('description6')
    ->label('label6')
    ->name('name6')
    ->build();
```

