
# Privileges

Security options for the container

## Structure

`Privileges`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `credentialSpec` | [`?CredentialSpec2`](../../doc/models/credential-spec-2.md) | Optional | - | getCredentialSpec(): ?CredentialSpec2 | setCredentialSpec(?CredentialSpec2 credentialSpec): void |
| `sELinuxContext` | [`?SELinuxContext2`](../../doc/models/se-linux-context-2.md) | Optional | - | getSELinuxContext(): ?SELinuxContext2 | setSELinuxContext(?SELinuxContext2 sELinuxContext): void |

## Example

```php
use DockerLib\Models\Builders\PrivilegesBuilder;
use DockerLib\Models\Builders\CredentialSpec2Builder;
use DockerLib\Models\Builders\SELinuxContext2Builder;

$privileges = PrivilegesBuilder::init()
    ->credentialSpec(
        CredentialSpec2Builder::init()
            ->file('File8')
            ->registry('Registry6')
            ->build()
    )
    ->sELinuxContext(
        SELinuxContext2Builder::init()
            ->disable(false)
            ->level('Level6')
            ->role('Role4')
            ->type('Type0')
            ->user('User6')
            ->build()
    )
    ->build();
```

