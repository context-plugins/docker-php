
# TLS Info

Information about the issuer of leaf TLS certificates and the trusted root CA certificate

## Structure

`TLSInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `certIssuerPublicKey` | `?string` | Optional | The base64-url-safe-encoded raw public key bytes of the issuer | getCertIssuerPublicKey(): ?string | setCertIssuerPublicKey(?string certIssuerPublicKey): void |
| `certIssuerSubject` | `?string` | Optional | The base64-url-safe-encoded raw subject bytes of the issuer | getCertIssuerSubject(): ?string | setCertIssuerSubject(?string certIssuerSubject): void |
| `trustRoot` | `?string` | Optional | The root CA certificate(s) that are used to validate leaf TLS certificates | getTrustRoot(): ?string | setTrustRoot(?string trustRoot): void |

## Example

```php
use DockerLib\Models\Builders\TLSInfoBuilder;

$tLSInfo = TLSInfoBuilder::init()
    ->certIssuerPublicKey('MFkwEwYHKoZIzj0CAQYIKoZIzj0DAQcDQgAEmT9XIw9h1qoNclv9VeHmf/Vi6/uI2vFXdBveXTpcPjqx6i9wNazchk1XWV/dKTKvSh9xyGKmiIeRcE4OiMnJ1A==')
    ->certIssuerSubject('MBMxETAPBgNVBAMTCHN3YXJtLWNh')
    ->trustRoot('-----BEGIN CERTIFICATE-----
MIIBajCCARCgAwIBAgIUbYqrLSOSQHoxD8CwG6Bi2PJi9c8wCgYIKoZIzj0EAwIw
EzERMA8GA1UEAxMIc3dhcm0tY2EwHhcNMTcwNDI0MjE0MzAwWhcNMzcwNDE5MjE0
MzAwWjATMREwDwYDVQQDEwhzd2FybS1jYTBZMBMGByqGSM49AgEGCCqGSM49AwEH
A0IABJk/VyMPYdaqDXJb/VXh5n/1Yuv7iNrxV3Qb3l06XD46seovcDWs3IZNV1lf
3Skyr0ofcchipoiHkXBODojJydSjQjBAMA4GA1UdDwEB/wQEAwIBBjAPBgNVHRMB
Af8EBTADAQH/MB0GA1UdDgQWBBRUXxuRcnFjDfR/RIAUQab8ZV/n4jAKBggqhkjO
PQQDAgNIADBFAiAy+JTe6Uc3KyLCMiqGl2GyWGQqQDEcO3/YG36x7om65AIhAJvz
pxv6zFeVEkAEEkqIYi0omA9+CjanB/6Bz4n1uw8H
-----END CERTIFICATE-----
')
    ->build();
```

