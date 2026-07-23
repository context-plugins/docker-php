
# Exec Start Request

## Structure

`ExecStartRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `detach` | `?bool` | Optional | Detach from the command. | getDetach(): ?bool | setDetach(?bool detach): void |
| `tty` | `?bool` | Optional | Allocate a pseudo-TTY. | getTty(): ?bool | setTty(?bool tty): void |

## Example

```php
use DockerLib\Models\Builders\ExecStartRequestBuilder;

$execStartRequest = ExecStartRequestBuilder::init()
    ->detach(false)
    ->tty(false)
    ->build();
```

