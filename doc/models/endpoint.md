
# Endpoint

## Structure

`Endpoint`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `ports` | [`?(EndpointPortConfig[])`](../../doc/models/endpoint-port-config.md) | Optional | - | getPorts(): ?array | setPorts(?array ports): void |
| `spec` | [`?Spec2`](../../doc/models/spec-2.md) | Optional | - | getSpec(): ?Spec2 | setSpec(?Spec2 spec): void |
| `virtualIPs` | [`?(VirtualIP[])`](../../doc/models/virtual-ip.md) | Optional | - | getVirtualIPs(): ?array | setVirtualIPs(?array virtualIPs): void |

## Example

```php
use DockerLib\Models\Builders\EndpointBuilder;
use DockerLib\Models\Builders\EndpointPortConfigBuilder;
use DockerLib\Models\Protocol1Enum;
use DockerLib\Models\Builders\Spec2Builder;
use DockerLib\Models\ModeEnum;
use DockerLib\Models\Builders\VirtualIPBuilder;

$endpoint = EndpointBuilder::init()
    ->ports(
        [
            EndpointPortConfigBuilder::init()
                ->name('Name6')
                ->protocol(Protocol1Enum::TCP)
                ->publishedPort(40)
                ->targetPort(114)
                ->build()
        ]
    )
    ->spec(
        Spec2Builder::init()
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
                        ->build()
                ]
            )
            ->build()
    )
    ->virtualIPs(
        [
            VirtualIPBuilder::init()
                ->addr('Addr6')
                ->networkID('NetworkID6')
                ->build()
        ]
    )
    ->build();
```

