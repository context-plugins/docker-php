
# Warning 1

## Structure

`Warning1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `digest` | `?string` | Optional | Digest of the image that caused the warning. | getDigest(): ?string | setDigest(?string digest): void |
| `repository` | `?string` | Optional | Name of the repository of the image that caused the warning. | getRepository(): ?string | setRepository(?string repository): void |
| `tags` | `?(string[])` | Optional | Current tags if warning is `current_tag`. | getTags(): ?array | setTags(?array tags): void |
| `warning` | [`?string(Warning2Enum)`](../../doc/models/warning-2-enum.md) | Optional | - | getWarning(): ?string | setWarning(?string warning): void |

## Example

```php
use DockerLib\Models\Builders\Warning1Builder;
use DockerLib\Models\Warning2Enum;

$warning1 = Warning1Builder::init()
    ->digest('sha256:1234567890abcdefghijklmnopqrstuvwxyz1234567890abcdefghijklmnopqr')
    ->repository('myrepo')
    ->tags(
        [
            'tags3',
            'tags4'
        ]
    )
    ->warning(Warning2Enum::IS_ACTIVE)
    ->build();
```

