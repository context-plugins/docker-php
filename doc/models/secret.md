
# Secret

## Structure

`Secret`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `createdAt` | `?string` | Optional | - | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `iD` | `?string` | Optional | - | getID(): ?string | setID(?string iD): void |
| `spec` | [`?SecretSpec`](../../doc/models/secret-spec.md) | Optional | - | getSpec(): ?SecretSpec | setSpec(?SecretSpec spec): void |
| `updatedAt` | `?string` | Optional | - | getUpdatedAt(): ?string | setUpdatedAt(?string updatedAt): void |
| `version` | [`?Version`](../../doc/models/version.md) | Optional | - | getVersion(): ?Version | setVersion(?Version version): void |

## Example

```php
use DockerLib\Models\Builders\SecretBuilder;
use DockerLib\Models\Builders\SecretSpecBuilder;
use DockerLib\Models\Builders\Driver1Builder;
use DockerLib\Models\Builders\VersionBuilder;

$secret = SecretBuilder::init()
    ->createdAt('2017-07-20T13:55:28.678958722Z')
    ->iD('blt1owaxmitz71s9v5zh81zun')
    ->spec(
        SecretSpecBuilder::init()
            ->data('Data6')
            ->driver(
                Driver1Builder::init(
                    'Name4'
                )
                    ->options(
                        [
                            'key0' => 'Options6'
                        ]
                    )
                    ->build()
            )
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
    ->updatedAt('2017-07-20T13:55:28.678958722Z')
    ->version(
        VersionBuilder::init()
            ->index(168)
            ->build()
    )
    ->build();
```

