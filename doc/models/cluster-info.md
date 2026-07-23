
# Cluster Info

ClusterInfo represents information about the swarm as is returned by the
"/info" endpoint. Join-tokens are not included.

## Structure

`ClusterInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `createdAt` | `?string` | Optional | Date and time at which the swarm was initialised in<br>[RFC 3339](https://www.ietf.org/rfc/rfc3339.txt) format with nano-seconds. | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `iD` | `?string` | Optional | The ID of the swarm. | getID(): ?string | setID(?string iD): void |
| `rootRotationInProgress` | `?bool` | Optional | Whether there is currently a root CA rotation in progress for the swarm | getRootRotationInProgress(): ?bool | setRootRotationInProgress(?bool rootRotationInProgress): void |
| `spec` | [`?Spec`](../../doc/models/spec.md) | Optional | - | getSpec(): ?Spec | setSpec(?Spec spec): void |
| `tLSInfo` | [`?TLSInfo1`](../../doc/models/tls-info-1.md) | Optional | - | getTLSInfo(): ?TLSInfo1 | setTLSInfo(?TLSInfo1 tLSInfo): void |
| `updatedAt` | `?string` | Optional | Date and time at which the swarm was last updated in<br>[RFC 3339](https://www.ietf.org/rfc/rfc3339.txt) format with nano-seconds. | getUpdatedAt(): ?string | setUpdatedAt(?string updatedAt): void |
| `version` | [`?Version`](../../doc/models/version.md) | Optional | - | getVersion(): ?Version | setVersion(?Version version): void |

## Example

```php
use DockerLib\Models\Builders\ClusterInfoBuilder;
use DockerLib\Models\Builders\SpecBuilder;
use DockerLib\ApiHelper;
use DockerLib\Models\Builders\EncryptionConfig2Builder;
use DockerLib\Models\Builders\TLSInfo1Builder;

$clusterInfo = ClusterInfoBuilder::init()
    ->createdAt('2016-08-18T10:44:24.496525531Z')
    ->iD('abajmipo7b4xz5ip2nrla6b11')
    ->rootRotationInProgress(false)
    ->spec(
        SpecBuilder::init()
            ->cAConfig(ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->dispatcher(ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->encryptionConfig(
                EncryptionConfig2Builder::init()
                    ->autoLockManagers(false)
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
    ->tLSInfo(
        TLSInfo1Builder::init()
            ->certIssuerPublicKey('CertIssuerPublicKey4')
            ->certIssuerSubject('CertIssuerSubject0')
            ->trustRoot('TrustRoot8')
            ->build()
    )
    ->updatedAt('2017-08-09T07:09:37.632105588Z')
    ->build();
```

