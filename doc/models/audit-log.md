
# Audit Log

Audit log event.

## Structure

`AuditLog`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `account` | `?string` | Optional | - | getAccount(): ?string | setAccount(?string account): void |
| `action` | `?string` | Optional | - | getAction(): ?string | setAction(?string action): void |
| `actionDescription` | `?string` | Optional | - | getActionDescription(): ?string | setActionDescription(?string actionDescription): void |
| `actor` | `?string` | Optional | - | getActor(): ?string | setActor(?string actor): void |
| `data` | `?array<string,string>` | Optional | - | getData(): ?array | setData(?array data): void |
| `name` | `?string` | Optional | - | getName(): ?string | setName(?string name): void |
| `timestamp` | `?DateTime` | Optional | - | getTimestamp(): ?\DateTime | setTimestamp(?\DateTime timestamp): void |

## Example

```php
use DockerLib\Models\Builders\AuditLogBuilder;

$auditLog = AuditLogBuilder::init()
    ->account('account0')
    ->action('action2')
    ->actionDescription('action_description4')
    ->actor('actor0')
    ->data(
        [
            'key0' => 'data5',
            'key1' => 'data6',
            'key2' => 'data7'
        ]
    )
    ->build();
```

