
# V2 Namespaces Delete Images Response

## Structure

`V2NamespacesDeleteImagesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `dryRun` | `?bool` | Optional | Whether the request was a dry run or not. | getDryRun(): ?bool | setDryRun(?bool dryRun): void |
| `metrics` | [`?Metrics`](../../doc/models/metrics.md) | Optional | - | getMetrics(): ?Metrics | setMetrics(?Metrics metrics): void |

## Example

```php
use DockerLib\Models\Builders\V2NamespacesDeleteImagesResponseBuilder;
use DockerLib\Models\Builders\MetricsBuilder;

$v2NamespacesDeleteImagesResponse = V2NamespacesDeleteImagesResponseBuilder::init()
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

