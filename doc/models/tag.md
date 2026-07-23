
# Tag

## Structure

`Tag`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `creator` | `?int` | Optional | ID of the user that pushed the tag | getCreator(): ?int | setCreator(?int creator): void |
| `fullSize` | `?int` | Optional | compressed size (sum of all layers) of the tagged image | getFullSize(): ?int | setFullSize(?int fullSize): void |
| `id` | `?int` | Optional | tag ID | getId(): ?int | setId(?int id): void |
| `images` | [`?Image1`](../../doc/models/image-1.md) | Optional | - | getImages(): ?Image1 | setImages(?Image1 images): void |
| `lastUpdated` | `?string` | Optional | datetime of last update | getLastUpdated(): ?string | setLastUpdated(?string lastUpdated): void |
| `lastUpdater` | `?int` | Optional | ID of the last user that updated the tag | getLastUpdater(): ?int | setLastUpdater(?int lastUpdater): void |
| `lastUpdaterUsername` | `?string` | Optional | Hub username of the user that updated the tag | getLastUpdaterUsername(): ?string | setLastUpdaterUsername(?string lastUpdaterUsername): void |
| `name` | `?string` | Optional | name of the tag | getName(): ?string | setName(?string name): void |
| `repository` | `?int` | Optional | repository ID | getRepository(): ?int | setRepository(?int repository): void |
| `status` | [`?string(Status21Enum)`](../../doc/models/status-21-enum.md) | Optional | - | getStatus(): ?string | setStatus(?string status): void |
| `tagLastPulled` | `?string` | Optional | datetime of last pull | getTagLastPulled(): ?string | setTagLastPulled(?string tagLastPulled): void |
| `tagLastPushed` | `?string` | Optional | datetime of last push | getTagLastPushed(): ?string | setTagLastPushed(?string tagLastPushed): void |
| `v2` | `?string` | Optional | repository API version | getV2(): ?string | setV2(?string v2): void |

## Example

```php
use DockerLib\Models\Builders\TagBuilder;
use DockerLib\Models\Builders\Image1Builder;

$tag = TagBuilder::init()
    ->creator(20)
    ->fullSize(26)
    ->id(168)
    ->images(
        Image1Builder::init()
            ->architecture('architecture0')
            ->digest('digest8')
            ->features('features6')
            ->lastPulled('last_pulled2')
            ->lastPushed('last_pushed4')
            ->build()
    )
    ->lastUpdated('2021-01-05T21:06:53.506400Z')
    ->tagLastPulled('2021-01-05T21:06:53.506400Z')
    ->tagLastPushed('2021-01-05T21:06:53.506400Z')
    ->build();
```

