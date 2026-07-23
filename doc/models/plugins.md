
# Plugins

## Structure

`Plugins`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `authorization` | `?(string[])` | Optional | Names of available authorization plugins. | getAuthorization(): ?array | setAuthorization(?array authorization): void |
| `log` | `?(string[])` | Optional | Names of available logging-drivers, and logging-driver plugins. | getLog(): ?array | setLog(?array log): void |
| `network` | `?(string[])` | Optional | Names of available network-drivers, and network-driver plugins. | getNetwork(): ?array | setNetwork(?array network): void |
| `volume` | `?(string[])` | Optional | Names of available volume-drivers, and network-driver plugins. | getVolume(): ?array | setVolume(?array volume): void |

## Example

```php
use DockerLib\Models\Builders\PluginsBuilder;

$plugins = PluginsBuilder::init()
    ->authorization(
        [
            'img-authz-plugin',
            'hbm'
        ]
    )
    ->log(
        [
            'awslogs',
            'fluentd',
            'gcplogs',
            'gelf',
            'journald',
            'json-file',
            'logentries',
            'splunk',
            'syslog'
        ]
    )
    ->network(
        [
            'bridge',
            'host',
            'ipvlan',
            'macvlan',
            'null',
            'overlay'
        ]
    )
    ->volume(
        [
            'local'
        ]
    )
    ->build();
```

