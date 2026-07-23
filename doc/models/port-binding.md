
# Port Binding

PortBinding represents a binding between a host IP address and a host
port.

## Structure

`PortBinding`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `hostIp` | `?string` | Optional | Host IP address that the container's port is mapped to. | getHostIp(): ?string | setHostIp(?string hostIp): void |
| `hostPort` | `?string` | Optional | Host port number that the container's port is mapped to. | getHostPort(): ?string | setHostPort(?string hostPort): void |

## Example

```php
use DockerLib\Models\Builders\PortBindingBuilder;

$portBinding = PortBindingBuilder::init()
    ->hostIp('127.0.0.1')
    ->hostPort('4443')
    ->build();
```

