
# Endpoint IPAM Config

EndpointIPAMConfig represents an endpoint's IPAM configuration.

## Structure

`EndpointIPAMConfig`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `iPv4Address` | `?string` | Optional | - | getIPv4Address(): ?string | setIPv4Address(?string iPv4Address): void |
| `iPv6Address` | `?string` | Optional | - | getIPv6Address(): ?string | setIPv6Address(?string iPv6Address): void |
| `linkLocalIPs` | `?(string[])` | Optional | - | getLinkLocalIPs(): ?array | setLinkLocalIPs(?array linkLocalIPs): void |

## Example

```php
use DockerLib\Models\Builders\EndpointIPAMConfigBuilder;

$endpointIPAMConfig = EndpointIPAMConfigBuilder::init()
    ->iPv4Address('172.20.30.33')
    ->iPv6Address('2001:db8:abcd::3033')
    ->linkLocalIPs(
        [
            '169.254.34.68',
            'fe80::3468'
        ]
    )
    ->build();
```

