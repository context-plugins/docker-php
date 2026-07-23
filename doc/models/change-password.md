
# Change Password

## Structure

`ChangePassword`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `supported` | `?bool` | Optional | - | getSupported(): ?bool | setSupported(?bool supported): void |

## Example

```php
use DockerLib\Models\Builders\ChangePasswordBuilder;

$changePassword = ChangePasswordBuilder::init()
    ->supported(false)
    ->build();
```

