
# Images Search Response

## Structure

`ImagesSearchResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `?string` | Optional | - | getDescription(): ?string | setDescription(?string description): void |
| `isAutomated` | `?bool` | Optional | - | getIsAutomated(): ?bool | setIsAutomated(?bool isAutomated): void |
| `isOfficial` | `?bool` | Optional | - | getIsOfficial(): ?bool | setIsOfficial(?bool isOfficial): void |
| `name` | `?string` | Optional | - | getName(): ?string | setName(?string name): void |
| `starCount` | `?int` | Optional | - | getStarCount(): ?int | setStarCount(?int starCount): void |

## Example

```php
use DockerLib\Models\Builders\ImagesSearchResponseBuilder;

$imagesSearchResponse = ImagesSearchResponseBuilder::init()
    ->description('description2')
    ->isAutomated(false)
    ->isOfficial(false)
    ->name('name8')
    ->starCount(242)
    ->build();
```

