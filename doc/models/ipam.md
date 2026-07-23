
# IPAM

## Structure

`IPAM`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `config` | `?(string[])` | Optional | List of IPAM configuration options, specified as a map: `{"Subnet": <CIDR>, "IPRange": <CIDR>, "Gateway": <IP address>, "AuxAddress": <device_name:IP address>}` | getConfig(): ?array | setConfig(?array config): void |
| `driver` | `?string` | Optional | Name of the IPAM driver to use.<br><br>**Default**: `'default'` | getDriver(): ?string | setDriver(?string driver): void |
| `options` | `?(string[])` | Optional | Driver-specific options, specified as a map. | getOptions(): ?array | setOptions(?array options): void |

## Example

```php
use DockerLib\Models\Builders\IPAMBuilder;

$iPAM = IPAMBuilder::init()
    ->config(
        [
            'Config0',
            'Config1'
        ]
    )
    ->driver('default')
    ->options(
        [
            'Options8',
            'Options9',
            'Options0'
        ]
    )
    ->build();
```

