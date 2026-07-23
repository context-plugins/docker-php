
# Metrics

## Structure

`Metrics`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `manifestDeletes` | `?int` | Optional | Number of manifests deleted. | getManifestDeletes(): ?int | setManifestDeletes(?int manifestDeletes): void |
| `manifestErrors` | `?int` | Optional | Number of manifests that failed to delete. | getManifestErrors(): ?int | setManifestErrors(?int manifestErrors): void |
| `tagDeletes` | `?int` | Optional | Number of tags deleted. | getTagDeletes(): ?int | setTagDeletes(?int tagDeletes): void |
| `tagErrors` | `?int` | Optional | Number of tags that failed to delete. | getTagErrors(): ?int | setTagErrors(?int tagErrors): void |

## Example

```php
use DockerLib\Models\Builders\MetricsBuilder;

$metrics = MetricsBuilder::init()
    ->manifestDeletes(3)
    ->manifestErrors(0)
    ->tagDeletes(1)
    ->tagErrors(0)
    ->build();
```

