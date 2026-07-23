
# Throttle Device

## Structure

`ThrottleDevice`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `path` | `?string` | Optional | Device path | getPath(): ?string | setPath(?string path): void |
| `rate` | `?int` | Optional | Rate<br><br>**Constraints**: `>= 0` | getRate(): ?int | setRate(?int rate): void |

## Example

```php
use DockerLib\Models\Builders\ThrottleDeviceBuilder;

$throttleDevice = ThrottleDeviceBuilder::init()
    ->path('Path8')
    ->rate(52)
    ->build();
```

