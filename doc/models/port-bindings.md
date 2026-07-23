
# Port Bindings

## Structure

`PortBindings`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `hostIp` | `?string` | Optional | The host IP address | getHostIp(): ?string | setHostIp(?string hostIp): void |
| `hostPort` | `?string` | Optional | The host port number, as a string | getHostPort(): ?string | setHostPort(?string hostPort): void |

## Example

```php
use DockerLib\Models\Builders\PortBindingsBuilder;

$portBindings = PortBindingsBuilder::init()
    ->hostIp('HostIp8')
    ->hostPort('HostPort4')
    ->build();
```

