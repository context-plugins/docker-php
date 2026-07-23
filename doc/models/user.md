
# User

## Structure

`User`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `gID` | `?int` | Optional | - | getGID(): ?int | setGID(?int gID): void |
| `uID` | `?int` | Optional | - | getUID(): ?int | setUID(?int uID): void |

## Example

```php
use DockerLib\Models\Builders\UserBuilder;

$user = UserBuilder::init()
    ->gID(1000)
    ->uID(1000)
    ->build();
```

