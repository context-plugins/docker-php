
# Networking Config 2

## Structure

`NetworkingConfig2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `endpointsConfig` | [`?array<string,EndpointSettings>`](../../doc/models/endpoint-settings.md) | Optional | A mapping of network name to endpoint configuration for that network. | getEndpointsConfig(): ?array | setEndpointsConfig(?array endpointsConfig): void |

## Example

```php
use DockerLib\Models\Builders\NetworkingConfig2Builder;
use DockerLib\Models\Builders\EndpointSettingsBuilder;

$networkingConfig2 = NetworkingConfig2Builder::init()
    ->endpointsConfig(
        [
            'key0' => EndpointSettingsBuilder::init()
                ->aliases(
                    [
                        'Aliases6',
                        'Aliases7'
                    ]
                )
                ->driverOpts(
                    [
                        'key0' => 'DriverOpts0',
                        'key1' => 'DriverOpts1'
                    ]
                )
                ->endpointID('EndpointID6')
                ->gateway('Gateway2')
                ->globalIPv6Address('GlobalIPv6Address6')
                ->build(),
            'key1' => EndpointSettingsBuilder::init()
                ->aliases(
                    [
                        'Aliases6',
                        'Aliases7'
                    ]
                )
                ->driverOpts(
                    [
                        'key0' => 'DriverOpts0',
                        'key1' => 'DriverOpts1'
                    ]
                )
                ->endpointID('EndpointID6')
                ->gateway('Gateway2')
                ->globalIPv6Address('GlobalIPv6Address6')
                ->build()
        ]
    )
    ->build();
```

