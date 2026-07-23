
# Graph Driver Data

Information about a container's graph driver.

## Structure

`GraphDriverData`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `data` | `array<string,string>` | Required | - | getData(): array | setData(array data): void |
| `name` | `string` | Required | - | getName(): string | setName(string name): void |

## Example

```php
use DockerLib\Models\Builders\GraphDriverDataBuilder;

$graphDriverData = GraphDriverDataBuilder::init(
    [
        'key0' => 'Data8'
    ],
    'Name2'
)->build();
```

