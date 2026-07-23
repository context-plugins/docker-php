
# Encryption Config

Parameters related to encryption-at-rest.

## Structure

`EncryptionConfig`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `autoLockManagers` | `?bool` | Optional | If set, generate a key and use it to lock data stored on the managers. | getAutoLockManagers(): ?bool | setAutoLockManagers(?bool autoLockManagers): void |

## Example

```php
use DockerLib\Models\Builders\EncryptionConfigBuilder;

$encryptionConfig = EncryptionConfigBuilder::init()
    ->autoLockManagers(false)
    ->build();
```

