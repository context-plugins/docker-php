
# Address

Address represents an IPv4 or IPv6 IP address.

## Structure

`Address`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `addr` | `?string` | Optional | IP address. | getAddr(): ?string | setAddr(?string addr): void |
| `prefixLen` | `?int` | Optional | Mask length of the IP address. | getPrefixLen(): ?int | setPrefixLen(?int prefixLen): void |

## Example

```php
use DockerLib\Models\Builders\AddressBuilder;

$address = AddressBuilder::init()
    ->addr('Addr0')
    ->prefixLen(202)
    ->build();
```

