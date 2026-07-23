
# Containers Changes Response

## Structure

`ContainersChangesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `kind` | [`int(KindEnum)`](../../doc/models/kind-enum.md) | Required | - | getKind(): int | setKind(int kind): void |
| `path` | `string` | Required | Path to file that has changed | getPath(): string | setPath(string path): void |

## Example

```php
use DockerLib\Models\Builders\ContainersChangesResponseBuilder;
use DockerLib\Models\KindEnum;

$containersChangesResponse = ContainersChangesResponseBuilder::init(
    KindEnum::ENUM_2,
    'Path8'
)->build();
```

