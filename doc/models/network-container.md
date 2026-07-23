
# Network Container

## Structure

`NetworkContainer`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `endpointID` | `?string` | Optional | - | getEndpointID(): ?string | setEndpointID(?string endpointID): void |
| `iPv4Address` | `?string` | Optional | - | getIPv4Address(): ?string | setIPv4Address(?string iPv4Address): void |
| `iPv6Address` | `?string` | Optional | - | getIPv6Address(): ?string | setIPv6Address(?string iPv6Address): void |
| `macAddress` | `?string` | Optional | - | getMacAddress(): ?string | setMacAddress(?string macAddress): void |
| `name` | `?string` | Optional | - | getName(): ?string | setName(?string name): void |

## Example

```php
use DockerLib\Models\Builders\NetworkContainerBuilder;

$networkContainer = NetworkContainerBuilder::init()
    ->endpointID('EndpointID8')
    ->iPv4Address('IPv4Address4')
    ->iPv6Address('IPv6Address8')
    ->macAddress('MacAddress4')
    ->name('Name0')
    ->build();
```

