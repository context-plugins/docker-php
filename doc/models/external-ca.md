
# External CA

## Structure

`ExternalCA`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cACert` | `?string` | Optional | The root CA certificate (in PEM format) this external CA uses to issue TLS certificates (assumed to be to the current swarm root CA certificate if not provided). | getCACert(): ?string | setCACert(?string cACert): void |
| `options` | `?array<string,string>` | Optional | An object with key/value pairs that are interpreted as protocol-specific options for the external CA driver. | getOptions(): ?array | setOptions(?array options): void |
| `protocol` | [`?string(ProtocolEnum)`](../../doc/models/protocol-enum.md) | Optional | - | getProtocol(): ?string | setProtocol(?string protocol): void |
| `uRL` | `?string` | Optional | URL where certificate signing requests should be sent. | getURL(): ?string | setURL(?string uRL): void |

## Example

```php
use DockerLib\Models\Builders\ExternalCABuilder;
use DockerLib\Models\ProtocolEnum;

$externalCA = ExternalCABuilder::init()
    ->cACert('CACert2')
    ->options(
        [
            'key0' => 'Options6'
        ]
    )
    ->protocol(ProtocolEnum::CFSSL)
    ->uRL('URL0')
    ->build();
```

