
# DNS Config 2

## Structure

`DNSConfig2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `nameservers` | `?(string[])` | Optional | The IP addresses of the name servers. | getNameservers(): ?array | setNameservers(?array nameservers): void |
| `options` | `?(string[])` | Optional | A list of internal resolver variables to be modified (e.g., `debug`, `ndots:3`, etc.). | getOptions(): ?array | setOptions(?array options): void |
| `search` | `?(string[])` | Optional | A search list for host-name lookup. | getSearch(): ?array | setSearch(?array search): void |

## Example

```php
use DockerLib\Models\Builders\DNSConfig2Builder;

$dNSConfig2 = DNSConfig2Builder::init()
    ->nameservers(
        [
            'Nameservers6'
        ]
    )
    ->options(
        [
            'Options6',
            'Options7',
            'Options8'
        ]
    )
    ->search(
        [
            'Search7',
            'Search8',
            'Search9'
        ]
    )
    ->build();
```

