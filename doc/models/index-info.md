
# Index Info

IndexInfo contains information about a registry.

## Structure

`IndexInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `mirrors` | `?(string[])` | Optional | List of mirrors, expressed as URIs. | getMirrors(): ?array | setMirrors(?array mirrors): void |
| `name` | `?string` | Optional | Name of the registry, such as "docker.io". | getName(): ?string | setName(?string name): void |
| `official` | `?bool` | Optional | Indicates whether this is an official registry (i.e., Docker Hub / docker.io) | getOfficial(): ?bool | setOfficial(?bool official): void |
| `secure` | `?bool` | Optional | Indicates if the the registry is part of the list of insecure<br>registries.<br><br>If `false`, the registry is insecure. Insecure registries accept<br>un-encrypted (HTTP) and/or untrusted (HTTPS with certificates from<br>unknown CAs) communication.<br><br>> **Warning**: Insecure registries can be useful when running a local<br>> registry. However, because its use creates security vulnerabilities<br>> it should ONLY be enabled for testing purposes. For increased<br>> security, users should add their CA to their system's list of<br>> trusted CAs instead of enabling this option. | getSecure(): ?bool | setSecure(?bool secure): void |

## Example

```php
use DockerLib\Models\Builders\IndexInfoBuilder;

$indexInfo = IndexInfoBuilder::init()
    ->mirrors(
        [
            'https://hub-mirror.corp.example.com:5000/',
            'https://registry-2.docker.io/',
            'https://registry-3.docker.io/'
        ]
    )
    ->name('docker.io')
    ->official(true)
    ->secure(true)
    ->build();
```

