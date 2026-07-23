
# Configs Create Response

## Structure

`ConfigsCreateResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `iD` | `?string` | Optional | The ID of the created config. | getID(): ?string | setID(?string iD): void |

## Example

```php
use DockerLib\Models\Builders\ConfigsCreateResponseBuilder;

$configsCreateResponse = ConfigsCreateResponseBuilder::init()
    ->iD('ktnbjxoalbkvbvedmg1urrz8h')
    ->build();
```

