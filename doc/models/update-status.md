
# Update Status

The status of a service update.

## Structure

`UpdateStatus`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `completedAt` | `?string` | Optional | - | getCompletedAt(): ?string | setCompletedAt(?string completedAt): void |
| `message` | `?string` | Optional | - | getMessage(): ?string | setMessage(?string message): void |
| `startedAt` | `?string` | Optional | - | getStartedAt(): ?string | setStartedAt(?string startedAt): void |
| `state` | [`?string(StateEnum)`](../../doc/models/state-enum.md) | Optional | - | getState(): ?string | setState(?string state): void |

## Example

```php
use DockerLib\Models\Builders\UpdateStatusBuilder;
use DockerLib\Models\StateEnum;

$updateStatus = UpdateStatusBuilder::init()
    ->completedAt('CompletedAt4')
    ->message('Message4')
    ->startedAt('StartedAt2')
    ->state(StateEnum::UPDATING)
    ->build();
```

