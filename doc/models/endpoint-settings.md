
# Endpoint Settings

Configuration for a network endpoint.

## Structure

`EndpointSettings`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `aliases` | `?(string[])` | Optional | - | getAliases(): ?array | setAliases(?array aliases): void |
| `driverOpts` | `?array<string,string>` | Optional | DriverOpts is a mapping of driver options and values. These options<br>are passed directly to the driver and are driver specific. | getDriverOpts(): ?array | setDriverOpts(?array driverOpts): void |
| `endpointID` | `?string` | Optional | Unique ID for the service endpoint in a Sandbox. | getEndpointID(): ?string | setEndpointID(?string endpointID): void |
| `gateway` | `?string` | Optional | Gateway address for this network. | getGateway(): ?string | setGateway(?string gateway): void |
| `globalIPv6Address` | `?string` | Optional | Global IPv6 address. | getGlobalIPv6Address(): ?string | setGlobalIPv6Address(?string globalIPv6Address): void |
| `globalIPv6PrefixLen` | `?int` | Optional | Mask length of the global IPv6 address. | getGlobalIPv6PrefixLen(): ?int | setGlobalIPv6PrefixLen(?int globalIPv6PrefixLen): void |
| `iPAMConfig` | `?array` | Optional | - | getIPAMConfig(): ?array | setIPAMConfig(?array iPAMConfig): void |
| `iPAddress` | `?string` | Optional | IPv4 address. | getIPAddress(): ?string | setIPAddress(?string iPAddress): void |
| `iPPrefixLen` | `?int` | Optional | Mask length of the IPv4 address. | getIPPrefixLen(): ?int | setIPPrefixLen(?int iPPrefixLen): void |
| `iPv6Gateway` | `?string` | Optional | IPv6 gateway address. | getIPv6Gateway(): ?string | setIPv6Gateway(?string iPv6Gateway): void |
| `links` | `?(string[])` | Optional | - | getLinks(): ?array | setLinks(?array links): void |
| `macAddress` | `?string` | Optional | MAC address for the endpoint on this network. | getMacAddress(): ?string | setMacAddress(?string macAddress): void |
| `networkID` | `?string` | Optional | Unique ID of the network. | getNetworkID(): ?string | setNetworkID(?string networkID): void |

## Example

```php
use DockerLib\Models\Builders\EndpointSettingsBuilder;

$endpointSettings = EndpointSettingsBuilder::init()
    ->aliases(
        [
            'server_x',
            'server_y'
        ]
    )
    ->driverOpts(
        [
            'com.example.some-label' => 'some-value',
            'com.example.some-other-label' => 'some-other-value'
        ]
    )
    ->endpointID('b88f5b905aabf2893f3cbc4ee42d1ea7980bbc0a92e2c8922b1e1795298afb0b')
    ->gateway('172.17.0.1')
    ->globalIPv6Address('2001:db8::5689')
    ->globalIPv6PrefixLen(64)
    ->iPAddress('172.17.0.4')
    ->iPPrefixLen(16)
    ->iPv6Gateway('2001:db8:2::100')
    ->links(
        [
            'container_1',
            'container_2'
        ]
    )
    ->macAddress('02:42:ac:11:00:04')
    ->networkID('08754567f1f40222263eab4102e1c733ae697e8e354aa9cd6e18d7402835292a')
    ->build();
```

