
# Engine

## Structure

`Engine`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `engineVersion` | `?string` | Optional | - | getEngineVersion(): ?string | setEngineVersion(?string engineVersion): void |
| `labels` | `?array<string,string>` | Optional | - | getLabels(): ?array | setLabels(?array labels): void |
| `plugins` | [`?(Plugin2[])`](../../doc/models/plugin-2.md) | Optional | - | getPlugins(): ?array | setPlugins(?array plugins): void |

## Example

```php
use DockerLib\Models\Builders\EngineBuilder;
use DockerLib\Models\Builders\Plugin2Builder;

$engine = EngineBuilder::init()
    ->engineVersion('17.06.0')
    ->labels(
        [
            'foo' => 'bar'
        ]
    )
    ->plugins(
        [
            Plugin2Builder::init()
                ->name('awslogs')
                ->type('Log')
                ->build(),
            Plugin2Builder::init()
                ->name('fluentd')
                ->type('Log')
                ->build(),
            Plugin2Builder::init()
                ->name('gcplogs')
                ->type('Log')
                ->build(),
            Plugin2Builder::init()
                ->name('gelf')
                ->type('Log')
                ->build(),
            Plugin2Builder::init()
                ->name('journald')
                ->type('Log')
                ->build(),
            Plugin2Builder::init()
                ->name('json-file')
                ->type('Log')
                ->build(),
            Plugin2Builder::init()
                ->name('logentries')
                ->type('Log')
                ->build(),
            Plugin2Builder::init()
                ->name('splunk')
                ->type('Log')
                ->build(),
            Plugin2Builder::init()
                ->name('syslog')
                ->type('Log')
                ->build(),
            Plugin2Builder::init()
                ->name('bridge')
                ->type('Network')
                ->build(),
            Plugin2Builder::init()
                ->name('host')
                ->type('Network')
                ->build(),
            Plugin2Builder::init()
                ->name('ipvlan')
                ->type('Network')
                ->build(),
            Plugin2Builder::init()
                ->name('macvlan')
                ->type('Network')
                ->build(),
            Plugin2Builder::init()
                ->name('null')
                ->type('Network')
                ->build(),
            Plugin2Builder::init()
                ->name('overlay')
                ->type('Network')
                ->build(),
            Plugin2Builder::init()
                ->name('local')
                ->type('Volume')
                ->build(),
            Plugin2Builder::init()
                ->name('localhost:5000/vieux/sshfs:latest')
                ->type('Volume')
                ->build(),
            Plugin2Builder::init()
                ->name('vieux/sshfs:latest')
                ->type('Volume')
                ->build()
        ]
    )
    ->build();
```

