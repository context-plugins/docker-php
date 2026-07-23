
# Port

An open port on a container

## Structure

`Port`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `iP` | `?string` | Optional | - | getIP(): ?string | setIP(?string iP): void |
| `privatePort` | `int` | Required | Port on the container | getPrivatePort(): int | setPrivatePort(int privatePort): void |
| `publicPort` | `?int` | Optional | Port exposed on the host | getPublicPort(): ?int | setPublicPort(?int publicPort): void |
| `type` | [`string(Type1Enum)`](../../doc/models/type-1-enum.md) | Required | - | getType(): string | setType(string type): void |

## Example

```php
use DockerLib\Models\Builders\PortBuilder;
use DockerLib\Models\Type1Enum;

$port = PortBuilder::init(
    8080,
    Type1Enum::TCP
)
    ->iP('IP6')
    ->publicPort(80)
    ->build();
```

