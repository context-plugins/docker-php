
# V2 Namespaces Repositories Images Summary Response

## Structure

`V2NamespacesRepositoriesImagesSummaryResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `activeFrom` | `?string` | Optional | Time from which an image must have been pushed or pulled to be counted as active. | getActiveFrom(): ?string | setActiveFrom(?string activeFrom): void |
| `statistics` | [`?Statistics`](../../doc/models/statistics.md) | Optional | - | getStatistics(): ?Statistics | setStatistics(?Statistics statistics): void |

## Example

```php
use DockerLib\Models\Builders\V2NamespacesRepositoriesImagesSummaryResponseBuilder;
use DockerLib\Models\Builders\StatisticsBuilder;

$v2NamespacesRepositoriesImagesSummaryResponse = V2NamespacesRepositoriesImagesSummaryResponseBuilder::init()
    ->activeFrom('2021-01-25T14:25:37.076343059Z')
    ->statistics(
        StatisticsBuilder::init()
            ->active(224)
            ->inactive(124)
            ->total(184)
            ->build()
    )
    ->build();
```

