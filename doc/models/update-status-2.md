
# Update Status 2

## Structure

`UpdateStatus2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `completedAt` | `?string` | Optional | - | getCompletedAt(): ?string | setCompletedAt(?string completedAt): void |
| `message` | `?string` | Optional | - | getMessage(): ?string | setMessage(?string message): void |
| `startedAt` | `?string` | Optional | - | getStartedAt(): ?string | setStartedAt(?string startedAt): void |
| `state` | [`?string(StateEnum)`](../../doc/models/state-enum.md) | Optional | - | getState(): ?string | setState(?string state): void |

## Example

```php
use DockerLib\Models\Builders\UpdateStatus2Builder;
use DockerLib\Models\StateEnum;

$updateStatus2 = UpdateStatus2Builder::init()
    ->completedAt('CompletedAt4')
    ->message('Message6')
    ->startedAt('StartedAt6')
    ->state(StateEnum::UPDATING)
    ->build();
```

