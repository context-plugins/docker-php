
# Ignore Warning

## Structure

`IgnoreWarning`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `digest` | `string` | Required | Digest of the image to ignore the warning for. | getDigest(): string | setDigest(string digest): void |
| `repository` | `string` | Required | Name of the repository of the image to ignore the warning for. | getRepository(): string | setRepository(string repository): void |
| `tags` | `?(string[])` | Optional | Current tags to ignore. | getTags(): ?array | setTags(?array tags): void |
| `warning` | [`string(WarningEnum)`](../../doc/models/warning-enum.md) | Required | - | getWarning(): string | setWarning(string warning): void |

## Example

```php
use DockerLib\Models\Builders\IgnoreWarningBuilder;
use DockerLib\Models\WarningEnum;

$ignoreWarning = IgnoreWarningBuilder::init(
    'sha256:1234567890abcdefghijklmnopqrstuvwxyz1234567890abcdefghijklmnopqr',
    'myrepo',
    WarningEnum::IS_ACTIVE
)
    ->tags(
        [
            'tags9'
        ]
    )
    ->build();
```

