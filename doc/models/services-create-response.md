
# Services Create Response

## Structure

`ServicesCreateResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `iD` | `?string` | Optional | The ID of the created service. | getID(): ?string | setID(?string iD): void |
| `warning` | `?string` | Optional | Optional warning message | getWarning(): ?string | setWarning(?string warning): void |

## Example

```php
use DockerLib\Models\Builders\ServicesCreateResponseBuilder;

$servicesCreateResponse = ServicesCreateResponseBuilder::init()
    ->iD('ak7w3gjqoa3kuz8xcpnyy0pvl')
    ->warning('unable to pin image doesnotexist:latest to digest: image library/doesnotexist:latest not found')
    ->build();
```

