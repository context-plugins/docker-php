
# Networks Create Response

## Structure

`NetworksCreateResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The ID of the created network. | getId(): ?string | setId(?string id): void |
| `warning` | `?string` | Optional | - | getWarning(): ?string | setWarning(?string warning): void |

## Example

```php
use DockerLib\Models\Builders\NetworksCreateResponseBuilder;

$networksCreateResponse = NetworksCreateResponseBuilder::init()
    ->id('22be93d5babb089c5aab8dbc369042fad48ff791584ca2da2100db837a1c7c30')
    ->warning('')
    ->build();
```

