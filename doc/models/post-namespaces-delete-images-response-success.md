
# Post Namespaces Delete Images Response Success

Successful delete images response.

## Structure

`PostNamespacesDeleteImagesResponseSuccess`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `dryRun` | `?bool` | Optional | Whether the request was a dry run or not. | getDryRun(): ?bool | setDryRun(?bool dryRun): void |
| `metrics` | [`?Metrics`](../../doc/models/metrics.md) | Optional | - | getMetrics(): ?Metrics | setMetrics(?Metrics metrics): void |

## Example

```php
use DockerLib\Models\Builders\PostNamespacesDeleteImagesResponseSuccessBuilder;
use DockerLib\Models\Builders\MetricsBuilder;

$postNamespacesDeleteImagesResponseSuccess = PostNamespacesDeleteImagesResponseSuccessBuilder::init()
    ->dryRun(false)
    ->metrics(
        MetricsBuilder::init()
            ->manifestDeletes(232)
            ->manifestErrors(34)
            ->tagDeletes(236)
            ->tagErrors(42)
            ->build()
    )
    ->build();
```

