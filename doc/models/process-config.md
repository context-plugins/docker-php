
# Process Config

## Structure

`ProcessConfig`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `arguments` | `?(string[])` | Optional | - | getArguments(): ?array | setArguments(?array arguments): void |
| `entrypoint` | `?string` | Optional | - | getEntrypoint(): ?string | setEntrypoint(?string entrypoint): void |
| `privileged` | `?bool` | Optional | - | getPrivileged(): ?bool | setPrivileged(?bool privileged): void |
| `tty` | `?bool` | Optional | - | getTty(): ?bool | setTty(?bool tty): void |
| `user` | `?string` | Optional | - | getUser(): ?string | setUser(?string user): void |

## Example

```php
use DockerLib\Models\Builders\ProcessConfigBuilder;

$processConfig = ProcessConfigBuilder::init()
    ->arguments(
        [
            'arguments1',
            'arguments2'
        ]
    )
    ->entrypoint('entrypoint2')
    ->privileged(false)
    ->tty(false)
    ->user('user8')
    ->build();
```

