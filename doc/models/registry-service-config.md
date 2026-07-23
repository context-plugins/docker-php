
# Registry Service Config

RegistryServiceConfig stores daemon registry services configuration.

## Structure

`RegistryServiceConfig`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `allowNondistributableArtifactsCIDRs` | `?(string[])` | Optional | List of IP ranges to which nondistributable artifacts can be pushed,<br>using the CIDR syntax [RFC 4632](https://tools.ietf.org/html/4632).<br><br>Some images (for example, Windows base images) contain artifacts<br>whose distribution is restricted by license. When these images are<br>pushed to a registry, restricted artifacts are not included.<br><br>This configuration override this behavior, and enables the daemon to<br>push nondistributable artifacts to all registries whose resolved IP<br>address is within the subnet described by the CIDR syntax.<br><br>This option is useful when pushing images containing<br>nondistributable artifacts to a registry on an air-gapped network so<br>hosts on that network can pull the images without connecting to<br>another server.<br><br>> **Warning**: Nondistributable artifacts typically have restrictions<br>> on how and where they can be distributed and shared. Only use this<br>> feature to push artifacts to private registries and ensure that you<br>> are in compliance with any terms that cover redistributing<br>> nondistributable artifacts. | getAllowNondistributableArtifactsCIDRs(): ?array | setAllowNondistributableArtifactsCIDRs(?array allowNondistributableArtifactsCIDRs): void |
| `allowNondistributableArtifactsHostnames` | `?(string[])` | Optional | List of registry hostnames to which nondistributable artifacts can be<br>pushed, using the format `<hostname>[:<port>]` or `<IP address>[:<port>]`.<br><br>Some images (for example, Windows base images) contain artifacts<br>whose distribution is restricted by license. When these images are<br>pushed to a registry, restricted artifacts are not included.<br><br>This configuration override this behavior for the specified<br>registries.<br><br>This option is useful when pushing images containing<br>nondistributable artifacts to a registry on an air-gapped network so<br>hosts on that network can pull the images without connecting to<br>another server.<br><br>> **Warning**: Nondistributable artifacts typically have restrictions<br>> on how and where they can be distributed and shared. Only use this<br>> feature to push artifacts to private registries and ensure that you<br>> are in compliance with any terms that cover redistributing<br>> nondistributable artifacts. | getAllowNondistributableArtifactsHostnames(): ?array | setAllowNondistributableArtifactsHostnames(?array allowNondistributableArtifactsHostnames): void |
| `indexConfigs` | array<string,array\|null\|[IndexInfo](../../doc/models/index-info.md)>\|null | Optional | This is Associative Array of a container for one-of cases. | getIndexConfigs(): ?array | setIndexConfigs(?array indexConfigs): void |
| `insecureRegistryCIDRs` | `?(string[])` | Optional | List of IP ranges of insecure registries, using the CIDR syntax<br>([RFC 4632](https://tools.ietf.org/html/4632)). Insecure registries<br>accept un-encrypted (HTTP) and/or untrusted (HTTPS with certificates<br>from unknown CAs) communication.<br><br>By default, local registries (`127.0.0.0/8`) are configured as<br>insecure. All other registries are secure. Communicating with an<br>insecure registry is not possible if the daemon assumes that registry<br>is secure.<br><br>This configuration override this behavior, insecure communication with<br>registries whose resolved IP address is within the subnet described by<br>the CIDR syntax.<br><br>Registries can also be marked insecure by hostname. Those registries<br>are listed under `IndexConfigs` and have their `Secure` field set to<br>`false`.<br><br>> **Warning**: Using this option can be useful when running a local<br>> registry, but introduces security vulnerabilities. This option<br>> should therefore ONLY be used for testing purposes. For increased<br>> security, users should add their CA to their system's list of trusted<br>> CAs instead of enabling this option. | getInsecureRegistryCIDRs(): ?array | setInsecureRegistryCIDRs(?array insecureRegistryCIDRs): void |
| `mirrors` | `?(string[])` | Optional | List of registry URLs that act as a mirror for the official<br>(`docker.io`) registry. | getMirrors(): ?array | setMirrors(?array mirrors): void |

## Example

```php
use DockerLib\Models\Builders\RegistryServiceConfigBuilder;
use DockerLib\ApiHelper;

$registryServiceConfig = RegistryServiceConfigBuilder::init()
    ->allowNondistributableArtifactsCIDRs(
        [
            '::1/128',
            '127.0.0.0/8'
        ]
    )
    ->allowNondistributableArtifactsHostnames(
        [
            'registry.internal.corp.example.com:3000',
            '[2001:db8:a0b:12f0::1]:443'
        ]
    )
    ->indexConfigs(
        [
            '127.0.0.1:5000' => ApiHelper::deserialize('{"Mirrors":[],"Name":"127.0.0.1:5000","Official":false,"Secure":false}'),
            '[2001:db8:a0b:12f0::1]:80' => ApiHelper::deserialize('{"Mirrors":[],"Name":"[2001:db8:a0b:12f0::1]:80","Official":false,"Secure":false}'),
            'docker.io' => ApiHelper::deserialize('{"Mirrors":["https://hub-mirror.corp.example.com:5000/"],"Name":"docker.io","Official":true,"Secure":true}'),
            'registry.internal.corp.example.com:3000' => ApiHelper::deserialize('{"Mirrors":[],"Name":"registry.internal.corp.example.com:3000","Official":false,"Secure":false}')
        ]
    )
    ->insecureRegistryCIDRs(
        [
            '::1/128',
            '127.0.0.0/8'
        ]
    )
    ->mirrors(
        [
            'https://hub-mirror.corp.example.com:5000/',
            'https://[2001:db8:a0b:12f0::1]/'
        ]
    )
    ->build();
```

