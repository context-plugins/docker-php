
# Network Settings 22

## Structure

`NetworkSettings22`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `networks` | [`?array<string,EndpointSettings>`](../../doc/models/endpoint-settings.md) | Optional | - | getNetworks(): ?array | setNetworks(?array networks): void |

## Example

```php
use DockerLib\Models\Builders\NetworkSettings22Builder;
use DockerLib\Models\Builders\EndpointSettingsBuilder;

$networkSettings22 = NetworkSettings22Builder::init()
    ->networks(
        [
            'key0' => EndpointSettingsBuilder::init()
                ->aliases(
                    [
                        'Aliases6',
                        'Aliases5',
                        'Aliases4'
                    ]
                )
                ->driverOpts(
                    [
                        'key0' => 'DriverOpts2',
                        'key1' => 'DriverOpts1',
                        'key2' => 'DriverOpts0'
                    ]
                )
                ->endpointID('EndpointID6')
                ->gateway('Gateway4')
                ->globalIPv6Address('GlobalIPv6Address4')
                ->build(),
            'key1' => EndpointSettingsBuilder::init()
                ->aliases(
                    [
                        'Aliases6',
                        'Aliases5',
                        'Aliases4'
                    ]
                )
                ->driverOpts(
                    [
                        'key0' => 'DriverOpts2',
                        'key1' => 'DriverOpts1',
                        'key2' => 'DriverOpts0'
                    ]
                )
                ->endpointID('EndpointID6')
                ->gateway('Gateway4')
                ->globalIPv6Address('GlobalIPv6Address4')
                ->build()
        ]
    )
    ->build();
```

