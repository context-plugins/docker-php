
# Credential Spec 2

## Structure

`CredentialSpec2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `file` | `?string` | Optional | Load credential spec from this file. The file is read by the daemon, and must be present in the<br>`CredentialSpecs` subdirectory in the docker data directory, which defaults to<br>`C:\ProgramData\Docker\` on Windows.<br><br>For example, specifying `spec.json` loads `C:\ProgramData\Docker\CredentialSpecs\spec.json`.<br><br><p><br /></p><br>> **Note**: `CredentialSpec.File` and `CredentialSpec.Registry` are mutually exclusive.<br> | getFile(): ?string | setFile(?string file): void |
| `registry` | `?string` | Optional | Load credential spec from this value in the Windows registry. The specified registry value must be<br>located in:<br><br>`HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Virtualization\Containers\CredentialSpecs`<br><br><p><br /></p><br>> **Note**: `CredentialSpec.File` and `CredentialSpec.Registry` are mutually exclusive.<br> | getRegistry(): ?string | setRegistry(?string registry): void |

## Example

```php
use DockerLib\Models\Builders\CredentialSpec2Builder;

$credentialSpec2 = CredentialSpec2Builder::init()
    ->file('File6')
    ->registry('Registry4')
    ->build();
```

