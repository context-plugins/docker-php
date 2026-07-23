
# Containers Wait Response

## Structure

`ContainersWaitResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `statusCode` | `int` | Required | Exit code of the container | getStatusCode(): int | setStatusCode(int statusCode): void |

## Example

```php
use DockerLib\Models\Builders\ContainersWaitResponseBuilder;

$containersWaitResponse = ContainersWaitResponseBuilder::init(
    60
)->build();
```

