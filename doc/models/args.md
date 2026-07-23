
# Args

## Structure

`Args`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `description` | `string` | Required | - | getDescription(): string | setDescription(string description): void |
| `name` | `string` | Required | - | getName(): string | setName(string name): void |
| `settable` | `string[]` | Required | - | getSettable(): array | setSettable(array settable): void |
| `value` | `string[]` | Required | - | getValue(): array | setValue(array value): void |

## Example

```php
use DockerLib\Models\Builders\ArgsBuilder;

$args = ArgsBuilder::init(
    'command line arguments',
    'args',
    [
        'Settable9',
        'Settable0',
        'Settable1'
    ],
    [
        'Value4'
    ]
)->build();
```

