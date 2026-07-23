
# Encryption Config 2

## Structure

`EncryptionConfig2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `autoLockManagers` | `?bool` | Optional | If set, generate a key and use it to lock data stored on the managers. | getAutoLockManagers(): ?bool | setAutoLockManagers(?bool autoLockManagers): void |

## Example

```php
use DockerLib\Models\Builders\EncryptionConfig2Builder;

$encryptionConfig2 = EncryptionConfig2Builder::init()
    ->autoLockManagers(false)
    ->build();
```

