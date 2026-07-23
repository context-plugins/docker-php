
# File

File represents a specific target that is backed by a file.

## Structure

`File`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `gID` | `?string` | Optional | GID represents the file GID. | getGID(): ?string | setGID(?string gID): void |
| `mode` | `?int` | Optional | Mode represents the FileMode of the file. | getMode(): ?int | setMode(?int mode): void |
| `name` | `?string` | Optional | Name represents the final filename in the filesystem. | getName(): ?string | setName(?string name): void |
| `uID` | `?string` | Optional | UID represents the file UID. | getUID(): ?string | setUID(?string uID): void |

## Example

```php
use DockerLib\Models\Builders\FileBuilder;

$file = FileBuilder::init()
    ->gID('GID0')
    ->mode(226)
    ->name('Name0')
    ->uID('UID0')
    ->build();
```

