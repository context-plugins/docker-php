
# Actor

## Structure

`Actor`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `attributes` | `?array<string,string>` | Optional | Various key/value attributes of the object, depending on its type | getAttributes(): ?array | setAttributes(?array attributes): void |
| `iD` | `?string` | Optional | The ID of the object emitting the event | getID(): ?string | setID(?string iD): void |

## Example

```php
use DockerLib\Models\Builders\ActorBuilder;

$actor = ActorBuilder::init()
    ->attributes(
        [
            'key0' => 'Attributes2',
            'key1' => 'Attributes3',
            'key2' => 'Attributes4'
        ]
    )
    ->iD('ID4')
    ->build();
```

