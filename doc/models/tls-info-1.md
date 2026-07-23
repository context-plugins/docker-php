
# TLS Info 1

## Structure

`TLSInfo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `certIssuerPublicKey` | `?string` | Optional | The base64-url-safe-encoded raw public key bytes of the issuer | getCertIssuerPublicKey(): ?string | setCertIssuerPublicKey(?string certIssuerPublicKey): void |
| `certIssuerSubject` | `?string` | Optional | The base64-url-safe-encoded raw subject bytes of the issuer | getCertIssuerSubject(): ?string | setCertIssuerSubject(?string certIssuerSubject): void |
| `trustRoot` | `?string` | Optional | The root CA certificate(s) that are used to validate leaf TLS certificates | getTrustRoot(): ?string | setTrustRoot(?string trustRoot): void |

## Example

```php
use DockerLib\Models\Builders\TLSInfo1Builder;

$tLSInfo1 = TLSInfo1Builder::init()
    ->certIssuerPublicKey('CertIssuerPublicKey8')
    ->certIssuerSubject('CertIssuerSubject4')
    ->trustRoot('TrustRoot2')
    ->build();
```

