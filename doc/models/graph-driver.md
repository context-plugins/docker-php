
# Graph Driver

## Structure

`GraphDriver`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `data` | `array<string,string>` | Required | - | getData(): array | setData(array data): void |
| `name` | `string` | Required | - | getName(): string | setName(string name): void |

## Example

```php
use DockerLib\Models\Builders\GraphDriverBuilder;

$graphDriver = GraphDriverBuilder::init(
    [
        'key0' => 'Data0',
        'key1' => 'Data1'
    ],
    'Name6'
)->build();
```

