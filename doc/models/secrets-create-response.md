
# Secrets Create Response

## Structure

`SecretsCreateResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `iD` | `?string` | Optional | The ID of the created secret. | getID(): ?string | setID(?string iD): void |

## Example

```php
use DockerLib\Models\Builders\SecretsCreateResponseBuilder;

$secretsCreateResponse = SecretsCreateResponseBuilder::init()
    ->iD('ktnbjxoalbkvbvedmg1urrz8h')
    ->build();
```

