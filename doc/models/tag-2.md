
# Tag 2

## Structure

`Tag2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `isCurrent` | `?bool` | Optional | `true` if the tag currently points to this image.<br><br>`false` if it has been overwritten to point at a different image. | getIsCurrent(): ?bool | setIsCurrent(?bool isCurrent): void |
| `tag` | `?string` | Optional | The tag. | getTag(): ?string | setTag(?string tag): void |

## Example

```php
use DockerLib\Models\Builders\Tag2Builder;

$tag2 = Tag2Builder::init()
    ->isCurrent(true)
    ->tag('latest')
    ->build();
```

