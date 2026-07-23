
# Get Namespace Repository Images Tags Response

Paginated list of tags for this repository.

## Structure

`GetNamespaceRepositoryImagesTagsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `count` | `?int` | Optional | Total count of tags for this image. | getCount(): ?int | setCount(?int count): void |
| `next` | `?string` | Optional | Link to the next page if there are more tags. | getNext(): ?string | setNext(?string next): void |
| `previous` | `?string` | Optional | Link to the previous page if not on first page. | getPrevious(): ?string | setPrevious(?string previous): void |
| `results` | [`?(Result1[])`](../../doc/models/result-1.md) | Optional | The current and historical tags for this image. | getResults(): ?array | setResults(?array results): void |

## Example

```php
use DockerLib\Models\Builders\GetNamespaceRepositoryImagesTagsResponseBuilder;
use DockerLib\Models\Builders\Result1Builder;

$getNamespaceRepositoryImagesTagsResponse = GetNamespaceRepositoryImagesTagsResponseBuilder::init()
    ->count(100)
    ->next('https://hub.docker.com/v2/namespaces/mynamespace/repositories/myrepo/images/sha256:mydigest/tags?&page=4&page_size=20')
    ->previous('https://hub.docker.com/v2/namespaces/mynamespace/repositories/myrepo/images/sha256:mydigest/tags?&page=2&page_size=20')
    ->results(
        [
            Result1Builder::init()
                ->isCurrent(false)
                ->tag('tag0')
                ->build(),
            Result1Builder::init()
                ->isCurrent(false)
                ->tag('tag0')
                ->build(),
            Result1Builder::init()
                ->isCurrent(false)
                ->tag('tag0')
                ->build()
        ]
    )
    ->build();
```

