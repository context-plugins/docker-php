
# Config

## Structure

`Config`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `createdAt` | `?string` | Optional | - | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `iD` | `?string` | Optional | - | getID(): ?string | setID(?string iD): void |
| `spec` | [`?ConfigSpec`](../../doc/models/config-spec.md) | Optional | - | getSpec(): ?ConfigSpec | setSpec(?ConfigSpec spec): void |
| `updatedAt` | `?string` | Optional | - | getUpdatedAt(): ?string | setUpdatedAt(?string updatedAt): void |
| `version` | [`?Version`](../../doc/models/version.md) | Optional | - | getVersion(): ?Version | setVersion(?Version version): void |

## Example

```php
use DockerLib\Models\Builders\ConfigBuilder;
use DockerLib\Models\Builders\ConfigSpecBuilder;
use DockerLib\Models\Builders\VersionBuilder;

$config = ConfigBuilder::init()
    ->createdAt('CreatedAt4')
    ->iD('ID0')
    ->spec(
        ConfigSpecBuilder::init()
            ->data('Data6')
            ->labels(
                [
                    'key0' => 'Labels0',
                    'key1' => 'Labels1',
                    'key2' => 'Labels2'
                ]
            )
            ->name('Name2')
            ->build()
    )
    ->updatedAt('UpdatedAt2')
    ->version(
        VersionBuilder::init()
            ->index(168)
            ->build()
    )
    ->build();
```

