
# Placement

## Structure

`Placement`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `constraints` | `?(string[])` | Optional | An array of constraints. | getConstraints(): ?array | setConstraints(?array constraints): void |
| `platforms` | [`?(Platform[])`](../../doc/models/platform.md) | Optional | Platforms stores all the platforms that the service's image can<br>run on. This field is used in the platform filter for scheduling.<br>If empty, then the platform filter is off, meaning there are no<br>scheduling restrictions. | getPlatforms(): ?array | setPlatforms(?array platforms): void |
| `preferences` | [`?(Preference[])`](../../doc/models/preference.md) | Optional | Preferences provide a way to make the scheduler aware of factors such as topology. They are provided in order from highest to lowest precedence. | getPreferences(): ?array | setPreferences(?array preferences): void |

## Example

```php
use DockerLib\Models\Builders\PlacementBuilder;
use DockerLib\Models\Builders\PlatformBuilder;
use DockerLib\Models\Builders\PreferenceBuilder;
use DockerLib\Models\Builders\SpreadBuilder;

$placement = PlacementBuilder::init()
    ->constraints(
        [
            'node.hostname!=node3.corp.example.com',
            'node.role!=manager',
            'node.labels.type==production'
        ]
    )
    ->platforms(
        [
            PlatformBuilder::init()
                ->architecture('Architecture2')
                ->oS('OS0')
                ->build(),
            PlatformBuilder::init()
                ->architecture('Architecture2')
                ->oS('OS0')
                ->build()
        ]
    )
    ->preferences(
        [
            PreferenceBuilder::init()
                ->spread(
                    SpreadBuilder::init()
                        ->spreadDescriptor('node.labels.datacenter')
                        ->build()
                )
                ->build(),
            PreferenceBuilder::init()
                ->spread(
                    SpreadBuilder::init()
                        ->spreadDescriptor('node.labels.rack')
                        ->build()
                )
                ->build()
        ]
    )
    ->build();
```

