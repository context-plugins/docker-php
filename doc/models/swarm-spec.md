
# Swarm Spec

User modifiable swarm configuration.

## Structure

`SwarmSpec`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cAConfig` | `?array` | Optional | - | getCAConfig(): ?array | setCAConfig(?array cAConfig): void |
| `dispatcher` | `?array` | Optional | - | getDispatcher(): ?array | setDispatcher(?array dispatcher): void |
| `encryptionConfig` | [`?EncryptionConfig2`](../../doc/models/encryption-config-2.md) | Optional | - | getEncryptionConfig(): ?EncryptionConfig2 | setEncryptionConfig(?EncryptionConfig2 encryptionConfig): void |
| `labels` | `?array<string,string>` | Optional | User-defined key/value metadata. | getLabels(): ?array | setLabels(?array labels): void |
| `name` | `?string` | Optional | Name of the swarm. | getName(): ?string | setName(?string name): void |
| `orchestration` | `?array` | Optional | - | getOrchestration(): ?array | setOrchestration(?array orchestration): void |
| `raft` | [`?Raft2`](../../doc/models/raft-2.md) | Optional | - | getRaft(): ?Raft2 | setRaft(?Raft2 raft): void |
| `taskDefaults` | [`?TaskDefaults2`](../../doc/models/task-defaults-2.md) | Optional | - | getTaskDefaults(): ?TaskDefaults2 | setTaskDefaults(?TaskDefaults2 taskDefaults): void |

## Example

```php
use DockerLib\Models\Builders\SwarmSpecBuilder;
use DockerLib\ApiHelper;
use DockerLib\Models\Builders\EncryptionConfig2Builder;

$swarmSpec = SwarmSpecBuilder::init()
    ->cAConfig(ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->dispatcher(ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->encryptionConfig(
        EncryptionConfig2Builder::init()
            ->autoLockManagers(false)
            ->build()
    )
    ->labels(
        [
            'com.example.corp.department' => 'engineering',
            'com.example.corp.type' => 'production'
        ]
    )
    ->name('default')
    ->build();
```

