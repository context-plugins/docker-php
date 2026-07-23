
# V2 Namespaces Delete Images Request

## Structure

`V2NamespacesDeleteImagesRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `activeFrom` | `?string` | Optional | Sets the time from which an image must have been pushed or pulled to<br>be counted as active.<br><br>Defaults to 1 month before the current time. | getActiveFrom(): ?string | setActiveFrom(?string activeFrom): void |
| `dryRun` | `?bool` | Optional | If `true` then will check and return errors and unignored warnings for the deletion request but will not delete any images. | getDryRun(): ?bool | setDryRun(?bool dryRun): void |
| `ignoreWarnings` | [`?(IgnoreWarning[])`](../../doc/models/ignore-warning.md) | Optional | Warnings to ignore. If a warning is not ignored then no deletions will happen and the<br>warning is returned in the response.<br><br>These warnings include:<br><br>- is_active: warning when attempting to delete an image that is marked as active.<br>- current_tag: warning when attempting to delete an image that has one or more current<br>  tags in the repository.<br><br>Warnings can be copied from the response to the request. | getIgnoreWarnings(): ?array | setIgnoreWarnings(?array ignoreWarnings): void |
| `manifests` | [`?(Manifest[])`](../../doc/models/manifest.md) | Optional | Image manifests to delete. | getManifests(): ?array | setManifests(?array manifests): void |

## Example

```php
use DockerLib\Models\Builders\V2NamespacesDeleteImagesRequestBuilder;
use DockerLib\Models\Builders\IgnoreWarningBuilder;
use DockerLib\Models\WarningEnum;
use DockerLib\Models\Builders\ManifestBuilder;

$v2NamespacesDeleteImagesRequest = V2NamespacesDeleteImagesRequestBuilder::init()
    ->activeFrom('2020-12-01T12:00:00Z')
    ->dryRun(false)
    ->ignoreWarnings(
        [
            IgnoreWarningBuilder::init(
                'digest4',
                'repository8',
                WarningEnum::IS_ACTIVE
            )
                ->tags(
                    [
                        'tags3'
                    ]
                )
                ->build(),
            IgnoreWarningBuilder::init(
                'digest4',
                'repository8',
                WarningEnum::IS_ACTIVE
            )
                ->tags(
                    [
                        'tags3'
                    ]
                )
                ->build(),
            IgnoreWarningBuilder::init(
                'digest4',
                'repository8',
                WarningEnum::IS_ACTIVE
            )
                ->tags(
                    [
                        'tags3'
                    ]
                )
                ->build()
        ]
    )
    ->manifests(
        [
            ManifestBuilder::init(
                'digest6',
                'repository0'
            )->build(),
            ManifestBuilder::init(
                'digest6',
                'repository0'
            )->build(),
            ManifestBuilder::init(
                'digest6',
                'repository0'
            )->build()
        ]
    )->build();
```

