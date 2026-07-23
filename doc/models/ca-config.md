
# CA Config

CA configuration.

## Structure

`CAConfig`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `externalCAs` | [`?(ExternalCA[])`](../../doc/models/external-ca.md) | Optional | Configuration for forwarding signing requests to an external certificate authority. | getExternalCAs(): ?array | setExternalCAs(?array externalCAs): void |
| `forceRotate` | `?int` | Optional | An integer whose purpose is to force swarm to generate a new signing CA certificate and key, if none have been specified in `SigningCACert` and `SigningCAKey` | getForceRotate(): ?int | setForceRotate(?int forceRotate): void |
| `nodeCertExpiry` | `?int` | Optional | The duration node certificates are issued for. | getNodeCertExpiry(): ?int | setNodeCertExpiry(?int nodeCertExpiry): void |
| `signingCACert` | `?string` | Optional | The desired signing CA certificate for all swarm node TLS leaf certificates, in PEM format. | getSigningCACert(): ?string | setSigningCACert(?string signingCACert): void |
| `signingCAKey` | `?string` | Optional | The desired signing CA key for all swarm node TLS leaf certificates, in PEM format. | getSigningCAKey(): ?string | setSigningCAKey(?string signingCAKey): void |

## Example

```php
use DockerLib\Models\Builders\CAConfigBuilder;
use DockerLib\Models\Builders\ExternalCABuilder;
use DockerLib\Models\ProtocolEnum;

$cAConfig = CAConfigBuilder::init()
    ->externalCAs(
        [
            ExternalCABuilder::init()
                ->cACert('CACert8')
                ->options(
                    [
                        'key0' => 'Options0',
                        'key1' => 'Options1',
                        'key2' => 'Options2'
                    ]
                )
                ->protocol(ProtocolEnum::CFSSL)
                ->uRL('URL6')
                ->build(),
            ExternalCABuilder::init()
                ->cACert('CACert8')
                ->options(
                    [
                        'key0' => 'Options0',
                        'key1' => 'Options1',
                        'key2' => 'Options2'
                    ]
                )
                ->protocol(ProtocolEnum::CFSSL)
                ->uRL('URL6')
                ->build(),
            ExternalCABuilder::init()
                ->cACert('CACert8')
                ->options(
                    [
                        'key0' => 'Options0',
                        'key1' => 'Options1',
                        'key2' => 'Options2'
                    ]
                )
                ->protocol(ProtocolEnum::CFSSL)
                ->uRL('URL6')
                ->build()
        ]
    )
    ->forceRotate(16)
    ->nodeCertExpiry(7776000000000000)
    ->signingCACert('SigningCACert2')
    ->signingCAKey('SigningCAKey6')
    ->build();
```

