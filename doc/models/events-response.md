
# Events Response

## Structure

`EventsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `action` | `?string` | Optional | The type of event | getAction(): ?string | setAction(?string action): void |
| `actor` | [`?Actor`](../../doc/models/actor.md) | Optional | - | getActor(): ?Actor | setActor(?Actor actor): void |
| `type` | `?string` | Optional | The type of object emitting the event | getType(): ?string | setType(?string type): void |
| `time` | `?int` | Optional | Timestamp of event | getTime(): ?int | setTime(?int time): void |
| `timeNano` | `?int` | Optional | Timestamp of event, with nanosecond accuracy | getTimeNano(): ?int | setTimeNano(?int timeNano): void |

## Example

```php
use DockerLib\Models\Builders\EventsResponseBuilder;
use DockerLib\Models\Builders\ActorBuilder;

$eventsResponse = EventsResponseBuilder::init()
    ->action('Action4')
    ->actor(
        ActorBuilder::init()
            ->attributes(
                [
                    'key0' => 'Attributes8',
                    'key1' => 'Attributes9'
                ]
            )
            ->iD('ID0')
            ->build()
    )
    ->type('Type4')
    ->time(218)
    ->timeNano(0)
    ->build();
```

