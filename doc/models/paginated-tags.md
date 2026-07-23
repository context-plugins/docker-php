
# Paginated Tags

## Structure

`PaginatedTags`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `count` | `?int` | Optional | total number of results available across all pages | getCount(): ?int | setCount(?int count): void |
| `next` | `?string` | Optional | link to next page of results if any | getNext(): ?string | setNext(?string next): void |
| `previous` | `?string` | Optional | link to previous page of results  if any | getPrevious(): ?string | setPrevious(?string previous): void |
| `results` | [`?(Tag[])`](../../doc/models/tag.md) | Optional | - | getResults(): ?array | setResults(?array results): void |

## Example

```php
use DockerLib\Models\Builders\PaginatedTagsBuilder;
use DockerLib\Models\Builders\TagBuilder;
use DockerLib\Models\Builders\Image1Builder;

$paginatedTags = PaginatedTagsBuilder::init()
    ->count(58)
    ->next('next8')
    ->previous('previous2')
    ->results(
        [
            TagBuilder::init()
                ->creator(54)
                ->fullSize(60)
                ->id(202)
                ->images(
                    Image1Builder::init()
                        ->architecture('architecture0')
                        ->digest('digest8')
                        ->features('features6')
                        ->lastPulled('last_pulled2')
                        ->lastPushed('last_pushed4')
                        ->build()
                )
                ->lastUpdated('last_updated2')
                ->build(),
            TagBuilder::init()
                ->creator(54)
                ->fullSize(60)
                ->id(202)
                ->images(
                    Image1Builder::init()
                        ->architecture('architecture0')
                        ->digest('digest8')
                        ->features('features6')
                        ->lastPulled('last_pulled2')
                        ->lastPushed('last_pushed4')
                        ->build()
                )
                ->lastUpdated('last_updated2')
                ->build()
        ]
    )
    ->build();
```

