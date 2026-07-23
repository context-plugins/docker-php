
# Task Defaults 2

## Structure

`TaskDefaults2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `logDriver` | [`?LogDriver3`](../../doc/models/log-driver-3.md) | Optional | - | getLogDriver(): ?LogDriver3 | setLogDriver(?LogDriver3 logDriver): void |

## Example

```php
use DockerLib\Models\Builders\TaskDefaults2Builder;
use DockerLib\Models\Builders\LogDriver3Builder;

$taskDefaults2 = TaskDefaults2Builder::init()
    ->logDriver(
        LogDriver3Builder::init()
            ->name('Name8')
            ->options(
                [
                    'key0' => 'Options0'
                ]
            )
            ->build()
    )
    ->build();
```

