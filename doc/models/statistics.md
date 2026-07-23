
# Statistics

## Structure

`Statistics`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `active` | `?int` | Optional | Number of images counted as active in this repository. | getActive(): ?int | setActive(?int active): void |
| `inactive` | `?int` | Optional | Number of images counted as inactive in this repository. | getInactive(): ?int | setInactive(?int inactive): void |
| `total` | `?int` | Optional | Number of images in this repository. | getTotal(): ?int | setTotal(?int total): void |

## Example

```php
use DockerLib\Models\Builders\StatisticsBuilder;

$statistics = StatisticsBuilder::init()
    ->active(2)
    ->inactive(1)
    ->total(3)
    ->build();
```

