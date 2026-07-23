
# Spec 2

## Structure

`Spec2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `mode` | [`?string(ModeEnum)`](../../doc/models/mode-enum.md) | Optional | - | getMode(): ?string | setMode(?string mode): void |
| `ports` | [`?(EndpointPortConfig[])`](../../doc/models/endpoint-port-config.md) | Optional | List of exposed ports that this service is accessible on from the outside. Ports can only be provided if `vip` resolution mode is used. | getPorts(): ?array | setPorts(?array ports): void |

## Example

```php
use DockerLib\Models\Builders\Spec2Builder;
use DockerLib\Models\ModeEnum;
use DockerLib\Models\Builders\EndpointPortConfigBuilder;
use DockerLib\Models\Protocol1Enum;

$spec2 = Spec2Builder::init()
    ->mode(ModeEnum::VIP)
    ->ports(
        [
            EndpointPortConfigBuilder::init()
                ->name('Name6')
                ->protocol(Protocol1Enum::TCP)
                ->publishedPort(40)
                ->targetPort(114)
                ->build(),
            EndpointPortConfigBuilder::init()
                ->name('Name6')
                ->protocol(Protocol1Enum::TCP)
                ->publishedPort(40)
                ->targetPort(114)
                ->build(),
            EndpointPortConfigBuilder::init()
                ->name('Name6')
                ->protocol(Protocol1Enum::TCP)
                ->publishedPort(40)
                ->targetPort(114)
                ->build()
        ]
    )
    ->build();
```

