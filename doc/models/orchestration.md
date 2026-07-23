
# Orchestration

Orchestration configuration.

## Structure

`Orchestration`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `taskHistoryRetentionLimit` | `?int` | Optional | The number of historic tasks to keep per instance or node. If negative, never remove completed or failed tasks. | getTaskHistoryRetentionLimit(): ?int | setTaskHistoryRetentionLimit(?int taskHistoryRetentionLimit): void |

## Example

```php
use DockerLib\Models\Builders\OrchestrationBuilder;

$orchestration = OrchestrationBuilder::init()
    ->taskHistoryRetentionLimit(10)
    ->build();
```

