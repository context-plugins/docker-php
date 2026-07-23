
# Virtual IP

## Structure

`VirtualIP`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `addr` | `?string` | Optional | - | getAddr(): ?string | setAddr(?string addr): void |
| `networkID` | `?string` | Optional | - | getNetworkID(): ?string | setNetworkID(?string networkID): void |

## Example

```php
use DockerLib\Models\Builders\VirtualIPBuilder;

$virtualIP = VirtualIPBuilder::init()
    ->addr('Addr8')
    ->networkID('NetworkID4')
    ->build();
```

