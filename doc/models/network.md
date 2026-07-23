
# Network

## Structure

`Network`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `attachable` | `?bool` | Optional | - | getAttachable(): ?bool | setAttachable(?bool attachable): void |
| `containers` | [`?array<string,NetworkContainer>`](../../doc/models/network-container.md) | Optional | - | getContainers(): ?array | setContainers(?array containers): void |
| `created` | `?string` | Optional | - | getCreated(): ?string | setCreated(?string created): void |
| `driver` | `?string` | Optional | - | getDriver(): ?string | setDriver(?string driver): void |
| `enableIPv6` | `?bool` | Optional | - | getEnableIPv6(): ?bool | setEnableIPv6(?bool enableIPv6): void |
| `iPAM` | [`?IPAM`](../../doc/models/ipam.md) | Optional | - | getIPAM(): ?IPAM | setIPAM(?IPAM iPAM): void |
| `id` | `?string` | Optional | - | getId(): ?string | setId(?string id): void |
| `ingress` | `?bool` | Optional | - | getIngress(): ?bool | setIngress(?bool ingress): void |
| `internal` | `?bool` | Optional | - | getInternal(): ?bool | setInternal(?bool internal): void |
| `labels` | `?array<string,string>` | Optional | - | getLabels(): ?array | setLabels(?array labels): void |
| `name` | `?string` | Optional | - | getName(): ?string | setName(?string name): void |
| `options` | `?array<string,string>` | Optional | - | getOptions(): ?array | setOptions(?array options): void |
| `scope` | `?string` | Optional | - | getScope(): ?string | setScope(?string scope): void |

## Example

```php
use DockerLib\Models\Builders\NetworkBuilder;
use DockerLib\Models\Builders\NetworkContainerBuilder;

$network = NetworkBuilder::init()
    ->attachable(false)
    ->containers(
        [
            'key0' => NetworkContainerBuilder::init()
                ->endpointID('EndpointID8')
                ->iPv4Address('IPv4Address2')
                ->iPv6Address('IPv6Address4')
                ->macAddress('MacAddress0')
                ->name('Name6')
                ->build()
        ]
    )
    ->created('Created8')
    ->driver('Driver0')
    ->enableIPv6(false)
    ->build();
```

