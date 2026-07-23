
# Config 2

## Structure

`Config2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `configID` | `?string` | Optional | ConfigID represents the ID of the specific config that we're referencing. | getConfigID(): ?string | setConfigID(?string configID): void |
| `configName` | `?string` | Optional | ConfigName is the name of the config that this references, but this is just provided for<br>lookup/display purposes. The config in the reference will be identified by its ID. | getConfigName(): ?string | setConfigName(?string configName): void |
| `file` | [`?File1`](../../doc/models/file-1.md) | Optional | - | getFile(): ?File1 | setFile(?File1 file): void |

## Example

```php
use DockerLib\Models\Builders\Config2Builder;
use DockerLib\Models\Builders\File1Builder;

$config2 = Config2Builder::init()
    ->configID('ConfigID0')
    ->configName('ConfigName2')
    ->file(
        File1Builder::init()
            ->gID('GID0')
            ->mode(224)
            ->name('Name0')
            ->uID('UID0')
            ->build()
    )
    ->build();
```

