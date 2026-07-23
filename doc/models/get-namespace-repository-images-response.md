
# Get Namespace Repository Images Response

Paginated list of images in a repository.

## Structure

`GetNamespaceRepositoryImagesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `count` | `?int` | Optional | Total count of images in the repository. | getCount(): ?int | setCount(?int count): void |
| `next` | `?string` | Optional | Link to the next page with the same query parameters if there are more images. | getNext(): ?string | setNext(?string next): void |
| `previous` | `?string` | Optional | Link to the previous page with the same query parameters if not on first page. | getPrevious(): ?string | setPrevious(?string previous): void |
| `results` | [`?(Result[])`](../../doc/models/result.md) | Optional | Image details. | getResults(): ?array | setResults(?array results): void |

## Example

```php
use DockerLib\Models\Builders\GetNamespaceRepositoryImagesResponseBuilder;
use DockerLib\Models\Builders\ResultBuilder;

$getNamespaceRepositoryImagesResponse = GetNamespaceRepositoryImagesResponseBuilder::init()
    ->count(100)
    ->next('https://hub.docker.com/v2/namespaces/mynamespace/repositories/myrepo/images?&page=4&page_size=20')
    ->previous('https://hub.docker.com/v2/namespaces/mynamespace/repositories/myrepo/images?&page=2&page_size=20')
    ->results(
        [
            ResultBuilder::init()
                ->digest('digest2')
                ->lastPulled('last_pulled8')
                ->lastPushed('last_pushed0')
                ->namespace('namespace6')
                ->repository('repository6')
                ->build()
        ]
    )
    ->build();
```

