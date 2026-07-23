
# Result

## Structure

`Result`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `digest` | `?string` | Optional | The image's digest. | getDigest(): ?string | setDigest(?string digest): void |
| `lastPulled` | `?string` | Optional | Time when this image was last pulled. Note this is updated at most once per hour. | getLastPulled(): ?string | setLastPulled(?string lastPulled): void |
| `lastPushed` | `?string` | Optional | Time when this image was last pushed. | getLastPushed(): ?string | setLastPushed(?string lastPushed): void |
| `namespace` | `?string` | Optional | The repository namespace. | getNamespace(): ?string | setNamespace(?string namespace): void |
| `repository` | `?string` | Optional | The repository name. | getRepository(): ?string | setRepository(?string repository): void |
| `status` | [`?string(Status2Enum)`](../../doc/models/status-2-enum.md) | Optional | - | getStatus(): ?string | setStatus(?string status): void |
| `tags` | [`?(Tag2[])`](../../doc/models/tag-2.md) | Optional | The current and historical tags for this image. | getTags(): ?array | setTags(?array tags): void |

## Example

```php
use DockerLib\Models\Builders\ResultBuilder;

$result = ResultBuilder::init()
    ->digest('sha256:1234567890abcdefghijklmnopqrstuvwxyz1234567890abcdefghijklmnopqr')
    ->lastPulled('2021-02-24T23:16:10.200008Z')
    ->lastPushed('2021-02-24T22:05:27.526308Z')
    ->namespace('mynamespace')
    ->repository('myrepo')
    ->build();
```

