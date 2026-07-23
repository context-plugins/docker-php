
# Manifest

## Structure

`Manifest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `digest` | `string` | Required | Digest of the image to delete. | getDigest(): string | setDigest(string digest): void |
| `repository` | `string` | Required | Name of the repository to delete the image from. | getRepository(): string | setRepository(string repository): void |

## Example

```php
use DockerLib\Models\Builders\ManifestBuilder;

$manifest = ManifestBuilder::init(
    'sha256:1234567890abcdefghijklmnopqrstuvwxyz1234567890abcdefghijklmnopqr',
    'myrepo'
)->build();
```

