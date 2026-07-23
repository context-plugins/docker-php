
# Network Settings

NetworkSettings exposes the network settings in the API

## Structure

`NetworkSettings`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `bridge` | `?string` | Optional | Name of the network'a bridge (for example, `docker0`). | getBridge(): ?string | setBridge(?string bridge): void |
| `endpointID` | `?string` | Optional | EndpointID uniquely represents a service endpoint in a Sandbox.<br><br><p><br /></p><br>> **Deprecated**: This field is only propagated when attached to the<br>> default "bridge" network. Use the information from the "bridge"<br>> network inside the `Networks` map instead, which contains the same<br>> information. This field was deprecated in Docker 1.9 and is scheduled<br>> to be removed in Docker 17.12.0<br> | getEndpointID(): ?string | setEndpointID(?string endpointID): void |
| `gateway` | `?string` | Optional | Gateway address for the default "bridge" network.<br><br><p><br /></p><br>> **Deprecated**: This field is only propagated when attached to the<br>> default "bridge" network. Use the information from the "bridge"<br>> network inside the `Networks` map instead, which contains the same<br>> information. This field was deprecated in Docker 1.9 and is scheduled<br>> to be removed in Docker 17.12.0<br> | getGateway(): ?string | setGateway(?string gateway): void |
| `globalIPv6Address` | `?string` | Optional | Global IPv6 address for the default "bridge" network.<br><br><p><br /></p><br>> **Deprecated**: This field is only propagated when attached to the<br>> default "bridge" network. Use the information from the "bridge"<br>> network inside the `Networks` map instead, which contains the same<br>> information. This field was deprecated in Docker 1.9 and is scheduled<br>> to be removed in Docker 17.12.0<br> | getGlobalIPv6Address(): ?string | setGlobalIPv6Address(?string globalIPv6Address): void |
| `globalIPv6PrefixLen` | `?int` | Optional | Mask length of the global IPv6 address.<br><br><p><br /></p><br>> **Deprecated**: This field is only propagated when attached to the<br>> default "bridge" network. Use the information from the "bridge"<br>> network inside the `Networks` map instead, which contains the same<br>> information. This field was deprecated in Docker 1.9 and is scheduled<br>> to be removed in Docker 17.12.0<br> | getGlobalIPv6PrefixLen(): ?int | setGlobalIPv6PrefixLen(?int globalIPv6PrefixLen): void |
| `hairpinMode` | `?bool` | Optional | Indicates if hairpin NAT should be enabled on the virtual interface. | getHairpinMode(): ?bool | setHairpinMode(?bool hairpinMode): void |
| `iPAddress` | `?string` | Optional | IPv4 address for the default "bridge" network.<br><br><p><br /></p><br>> **Deprecated**: This field is only propagated when attached to the<br>> default "bridge" network. Use the information from the "bridge"<br>> network inside the `Networks` map instead, which contains the same<br>> information. This field was deprecated in Docker 1.9 and is scheduled<br>> to be removed in Docker 17.12.0<br> | getIPAddress(): ?string | setIPAddress(?string iPAddress): void |
| `iPPrefixLen` | `?int` | Optional | Mask length of the IPv4 address.<br><br><p><br /></p><br>> **Deprecated**: This field is only propagated when attached to the<br>> default "bridge" network. Use the information from the "bridge"<br>> network inside the `Networks` map instead, which contains the same<br>> information. This field was deprecated in Docker 1.9 and is scheduled<br>> to be removed in Docker 17.12.0<br> | getIPPrefixLen(): ?int | setIPPrefixLen(?int iPPrefixLen): void |
| `iPv6Gateway` | `?string` | Optional | IPv6 gateway address for this network.<br><br><p><br /></p><br>> **Deprecated**: This field is only propagated when attached to the<br>> default "bridge" network. Use the information from the "bridge"<br>> network inside the `Networks` map instead, which contains the same<br>> information. This field was deprecated in Docker 1.9 and is scheduled<br>> to be removed in Docker 17.12.0<br> | getIPv6Gateway(): ?string | setIPv6Gateway(?string iPv6Gateway): void |
| `linkLocalIPv6Address` | `?string` | Optional | IPv6 unicast address using the link-local prefix. | getLinkLocalIPv6Address(): ?string | setLinkLocalIPv6Address(?string linkLocalIPv6Address): void |
| `linkLocalIPv6PrefixLen` | `?int` | Optional | Prefix length of the IPv6 unicast address. | getLinkLocalIPv6PrefixLen(): ?int | setLinkLocalIPv6PrefixLen(?int linkLocalIPv6PrefixLen): void |
| `macAddress` | `?string` | Optional | MAC address for the container on the default "bridge" network.<br><br><p><br /></p><br>> **Deprecated**: This field is only propagated when attached to the<br>> default "bridge" network. Use the information from the "bridge"<br>> network inside the `Networks` map instead, which contains the same<br>> information. This field was deprecated in Docker 1.9 and is scheduled<br>> to be removed in Docker 17.12.0<br> | getMacAddress(): ?string | setMacAddress(?string macAddress): void |
| `networks` | [`?array<string,EndpointSettings>`](../../doc/models/endpoint-settings.md) | Optional | Information about all networks that the container is connected to. | getNetworks(): ?array | setNetworks(?array networks): void |
| `ports` | `?array` | Optional | PortMap describes the mapping of container ports to host ports, using the<br>container's port-number and protocol as key in the format `<port>/<protocol>`,<br>for example, `80/udp`.<br><br>If a container's port is mapped for both `tcp` and `udp`, two separate<br>entries are added to the mapping table. | getPorts(): ?array | setPorts(?array ports): void |
| `sandboxID` | `?string` | Optional | SandboxID uniquely represents a container's network stack. | getSandboxID(): ?string | setSandboxID(?string sandboxID): void |
| `sandboxKey` | `?string` | Optional | SandboxKey identifies the sandbox | getSandboxKey(): ?string | setSandboxKey(?string sandboxKey): void |
| `secondaryIPAddresses` | [`?(Address[])`](../../doc/models/address.md) | Optional | - | getSecondaryIPAddresses(): ?array | setSecondaryIPAddresses(?array secondaryIPAddresses): void |
| `secondaryIPv6Addresses` | [`?(Address[])`](../../doc/models/address.md) | Optional | - | getSecondaryIPv6Addresses(): ?array | setSecondaryIPv6Addresses(?array secondaryIPv6Addresses): void |

## Example

```php
use DockerLib\Models\Builders\NetworkSettingsBuilder;
use DockerLib\ApiHelper;

$networkSettings = NetworkSettingsBuilder::init()
    ->bridge('docker0')
    ->endpointID('b88f5b905aabf2893f3cbc4ee42d1ea7980bbc0a92e2c8922b1e1795298afb0b')
    ->gateway('172.17.0.1')
    ->globalIPv6Address('2001:db8::5689')
    ->globalIPv6PrefixLen(64)
    ->hairpinMode(false)
    ->iPAddress('172.17.0.4')
    ->iPPrefixLen(16)
    ->iPv6Gateway('2001:db8:2::100')
    ->linkLocalIPv6Address('fe80::42:acff:fe11:1')
    ->linkLocalIPv6PrefixLen(64)
    ->macAddress('02:42:ac:11:00:04')
    ->ports(
        [
            '2377/tcp' => [],
            '443/tcp' => ApiHelper::deserialize('[{"HostIp":"127.0.0.1","HostPort":"4443"}]'),
            '53/udp' => ApiHelper::deserialize('[{"HostIp":"0.0.0.0","HostPort":"53"}]'),
            '80/tcp' => ApiHelper::deserialize('[{"HostIp":"0.0.0.0","HostPort":"80"},{"HostIp":"0.0.0.0","HostPort":"8080"}]'),
            '80/udp' => ApiHelper::deserialize('[{"HostIp":"0.0.0.0","HostPort":"80"}]')
        ]
    )
    ->sandboxID('9d12daf2c33f5959c8bf90aa513e4f65b561738661003029ec84830cd503a0c3')
    ->sandboxKey('/var/run/docker/netns/8ab54b426c38')
    ->build();
```

