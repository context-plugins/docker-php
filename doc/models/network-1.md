
# Network 1

## Structure

`Network1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | `string` | Required | - | getType(): string | setType(string type): void |

## Example

```php
use DockerLib\Models\Builders\Network1Builder;

$network1 = Network1Builder::init(
    'host'
)->build();
```

