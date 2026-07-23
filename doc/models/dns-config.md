
# DNS Config

Specification for DNS related configurations in resolver configuration file (`resolv.conf`).

## Structure

`DNSConfig`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `nameservers` | `?(string[])` | Optional | The IP addresses of the name servers. | getNameservers(): ?array | setNameservers(?array nameservers): void |
| `options` | `?(string[])` | Optional | A list of internal resolver variables to be modified (e.g., `debug`, `ndots:3`, etc.). | getOptions(): ?array | setOptions(?array options): void |
| `search` | `?(string[])` | Optional | A search list for host-name lookup. | getSearch(): ?array | setSearch(?array search): void |

## Example

```php
use DockerLib\Models\Builders\DNSConfigBuilder;

$dNSConfig = DNSConfigBuilder::init()
    ->nameservers(
        [
            'Nameservers6',
            'Nameservers5'
        ]
    )
    ->options(
        [
            'Options4'
        ]
    )
    ->search(
        [
            'Search5'
        ]
    )
    ->build();
```

