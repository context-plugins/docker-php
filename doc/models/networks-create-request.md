
# Networks Create Request

## Structure

`NetworksCreateRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `attachable` | `?bool` | Optional | Globally scoped network is manually attachable by regular containers from workers in swarm mode. | getAttachable(): ?bool | setAttachable(?bool attachable): void |
| `checkDuplicate` | `?bool` | Optional | Check for networks with duplicate names. Since Network is primarily keyed based on a random ID and not on the name, and network name is strictly a user-friendly alias to the network which is uniquely identified using ID, there is no guaranteed way to check for duplicates. CheckDuplicate is there to provide a best effort checking of any networks which has the same name but it is not guaranteed to catch all name collisions. | getCheckDuplicate(): ?bool | setCheckDuplicate(?bool checkDuplicate): void |
| `driver` | `?string` | Optional | Name of the network driver plugin to use.<br><br>**Default**: `'bridge'` | getDriver(): ?string | setDriver(?string driver): void |
| `enableIPv6` | `?bool` | Optional | Enable IPv6 on the network. | getEnableIPv6(): ?bool | setEnableIPv6(?bool enableIPv6): void |
| `iPAM` | [`?IPAM`](../../doc/models/ipam.md) | Optional | - | getIPAM(): ?IPAM | setIPAM(?IPAM iPAM): void |
| `ingress` | `?bool` | Optional | Ingress network is the network which provides the routing-mesh in swarm mode. | getIngress(): ?bool | setIngress(?bool ingress): void |
| `internal` | `?bool` | Optional | Restrict external access to the network. | getInternal(): ?bool | setInternal(?bool internal): void |
| `labels` | `?array<string,string>` | Optional | User-defined key/value metadata. | getLabels(): ?array | setLabels(?array labels): void |
| `name` | `string` | Required | The network's name. | getName(): string | setName(string name): void |
| `options` | `?array<string,string>` | Optional | Network specific options to be used by the drivers. | getOptions(): ?array | setOptions(?array options): void |

## Example

```php
use DockerLib\Models\Builders\NetworksCreateRequestBuilder;
use DockerLib\Models\Builders\IPAMBuilder;

$networksCreateRequest = NetworksCreateRequestBuilder::init(
    'Name6'
)
    ->attachable(false)
    ->checkDuplicate(false)
    ->driver('bridge')
    ->enableIPv6(false)
    ->iPAM(
        IPAMBuilder::init()
            ->config(
                [
                    'Config8',
                    'Config9',
                    'Config0'
                ]
            )
            ->driver('Driver0')
            ->options(
                [
                    'Options4'
                ]
            )
            ->build()
    )
    ->build();
```

