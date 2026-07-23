
# Log Driver

The log driver to use for tasks created in the orchestrator if
unspecified by a service.

Updating this value only affects new tasks. Existing tasks continue
to use their previously configured log driver until recreated.

## Structure

`LogDriver`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | The log driver to use as a default for new tasks. | getName(): ?string | setName(?string name): void |
| `options` | `?array<string,string>` | Optional | Driver-specific options for the selectd log driver, specified<br>as key/value pairs. | getOptions(): ?array | setOptions(?array options): void |

## Example

```php
use DockerLib\Models\Builders\LogDriverBuilder;

$logDriver = LogDriverBuilder::init()
    ->name('json-file')
    ->options(
        [
            'max-file' => '10',
            'max-size' => '100m'
        ]
    )
    ->build();
```

