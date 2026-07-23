
# Secret 1

## Structure

`Secret1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `file` | [`?File1`](../../doc/models/file-1.md) | Optional | - | getFile(): ?File1 | setFile(?File1 file): void |
| `secretID` | `?string` | Optional | SecretID represents the ID of the specific secret that we're referencing. | getSecretID(): ?string | setSecretID(?string secretID): void |
| `secretName` | `?string` | Optional | SecretName is the name of the secret that this references, but this is just provided for<br>lookup/display purposes. The secret in the reference will be identified by its ID. | getSecretName(): ?string | setSecretName(?string secretName): void |

## Example

```php
use DockerLib\Models\Builders\Secret1Builder;
use DockerLib\Models\Builders\File1Builder;

$secret1 = Secret1Builder::init()
    ->file(
        File1Builder::init()
            ->gID('GID0')
            ->mode(224)
            ->name('Name0')
            ->uID('UID0')
            ->build()
    )
    ->secretID('SecretID2')
    ->secretName('SecretName4')
    ->build();
```

