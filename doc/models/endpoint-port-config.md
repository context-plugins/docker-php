
# Endpoint Port Config

## Structure

`EndpointPortConfig`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | - | getName(): ?string | setName(?string name): void |
| `protocol` | [`?string(Protocol1Enum)`](../../doc/models/protocol-1-enum.md) | Optional | - | getProtocol(): ?string | setProtocol(?string protocol): void |
| `publishedPort` | `?int` | Optional | The port on the swarm hosts. | getPublishedPort(): ?int | setPublishedPort(?int publishedPort): void |
| `targetPort` | `?int` | Optional | The port inside the container. | getTargetPort(): ?int | setTargetPort(?int targetPort): void |

## Example

```php
use DockerLib\Models\Builders\EndpointPortConfigBuilder;
use DockerLib\Models\Protocol1Enum;

$endpointPortConfig = EndpointPortConfigBuilder::init()
    ->name('Name8')
    ->protocol(Protocol1Enum::TCP)
    ->publishedPort(212)
    ->targetPort(30)
    ->build();
```

