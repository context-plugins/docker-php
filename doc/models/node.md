
# Node

## Structure

`Node`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `createdAt` | `?string` | Optional | Date and time at which the node was added to the swarm in<br>[RFC 3339](https://www.ietf.org/rfc/rfc3339.txt) format with nano-seconds. | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `description` | [`?Description`](../../doc/models/description.md) | Optional | - | getDescription(): ?Description | setDescription(?Description description): void |
| `iD` | `?string` | Optional | - | getID(): ?string | setID(?string iD): void |
| `managerStatus` | `?array` | Optional | - | getManagerStatus(): ?array | setManagerStatus(?array managerStatus): void |
| `spec` | [`?NodeSpec`](../../doc/models/node-spec.md) | Optional | - | getSpec(): ?NodeSpec | setSpec(?NodeSpec spec): void |
| `status` | [`?Status4`](../../doc/models/status-4.md) | Optional | - | getStatus(): ?Status4 | setStatus(?Status4 status): void |
| `updatedAt` | `?string` | Optional | Date and time at which the node was last updated in<br>[RFC 3339](https://www.ietf.org/rfc/rfc3339.txt) format with nano-seconds. | getUpdatedAt(): ?string | setUpdatedAt(?string updatedAt): void |
| `version` | [`?Version`](../../doc/models/version.md) | Optional | - | getVersion(): ?Version | setVersion(?Version version): void |

## Example

```php
use DockerLib\Models\Builders\NodeBuilder;
use DockerLib\Models\Builders\DescriptionBuilder;
use DockerLib\Models\Builders\EngineBuilder;
use DockerLib\Models\Builders\Platform2Builder;
use DockerLib\Models\Builders\Resources3Builder;
use DockerLib\Models\Builders\GenericResourceBuilder;
use DockerLib\Models\Builders\TLSInfo1Builder;
use DockerLib\ApiHelper;
use DockerLib\Models\Builders\NodeSpecBuilder;
use DockerLib\Models\AvailabilityEnum;
use DockerLib\Models\RoleEnum;

$node = NodeBuilder::init()
    ->createdAt('2016-08-18T10:44:24.496525531Z')
    ->description(
        DescriptionBuilder::init()
            ->engine(
                EngineBuilder::init()
                    ->engineVersion('EngineVersion2')
                    ->labels(
                        [
                            'key0' => 'Labels8',
                            'key1' => 'Labels9'
                        ]
                    )
                    ->plugins(
                        [
                            null
                        ]
                    )
                    ->build()
            )
            ->hostname('Hostname2')
            ->platform(
                Platform2Builder::init()
                    ->architecture('Architecture6')
                    ->oS('OS4')
                    ->build()
            )
            ->resources(
                Resources3Builder::init()
                    ->genericResources(
                        [
                            null,
                            GenericResourceBuilder::init()->build()
                        ]
                    )
                    ->memoryBytes(152)
                    ->nanoCPUs(176)
                    ->build()
            )
            ->tLSInfo(
                TLSInfo1Builder::init()
                    ->certIssuerPublicKey('CertIssuerPublicKey4')
                    ->certIssuerSubject('CertIssuerSubject0')
                    ->trustRoot('TrustRoot8')
                    ->build()
            )
            ->build()
    )
    ->iD('24ifsmvkjbyhk')
    ->managerStatus(ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->spec(
        NodeSpecBuilder::init()
            ->availability(AvailabilityEnum::ACTIVE)
            ->labels(
                [
                    'key0' => 'Labels0',
                    'key1' => 'Labels1',
                    'key2' => 'Labels2'
                ]
            )
            ->name('Name2')
            ->role(RoleEnum::WORKER)
            ->build()
    )
    ->updatedAt('2017-08-09T07:09:37.632105588Z')
    ->build();
```

