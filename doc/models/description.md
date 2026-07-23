
# Description

## Structure

`Description`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `engine` | [`?Engine`](../../doc/models/engine.md) | Optional | - | getEngine(): ?Engine | setEngine(?Engine engine): void |
| `hostname` | `?string` | Optional | - | getHostname(): ?string | setHostname(?string hostname): void |
| `platform` | [`?Platform2`](../../doc/models/platform-2.md) | Optional | - | getPlatform(): ?Platform2 | setPlatform(?Platform2 platform): void |
| `resources` | [`?Resources3`](../../doc/models/resources-3.md) | Optional | - | getResources(): ?Resources3 | setResources(?Resources3 resources): void |
| `tLSInfo` | [`?TLSInfo1`](../../doc/models/tls-info-1.md) | Optional | - | getTLSInfo(): ?TLSInfo1 | setTLSInfo(?TLSInfo1 tLSInfo): void |

## Example

```php
use DockerLib\Models\Builders\DescriptionBuilder;
use DockerLib\Models\Builders\EngineBuilder;
use DockerLib\Models\Builders\Platform2Builder;
use DockerLib\Models\Builders\Resources3Builder;
use DockerLib\Models\Builders\GenericResourceBuilder;
use DockerLib\Models\Builders\TLSInfo1Builder;

$description = DescriptionBuilder::init()
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
    ->hostname('bf3067039e47')
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
    ->build();
```

