
# Volume

## Structure

`Volume`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `createdAt` | `?string` | Optional | Date/Time the volume was created. | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `driver` | `string` | Required | Name of the volume driver used by the volume. | getDriver(): string | setDriver(string driver): void |
| `labels` | `array<string,string>` | Required | User-defined key/value metadata. | getLabels(): array | setLabels(array labels): void |
| `mountpoint` | `string` | Required | Mount path of the volume on the host. | getMountpoint(): string | setMountpoint(string mountpoint): void |
| `name` | `string` | Required | Name of the volume. | getName(): string | setName(string name): void |
| `options` | `array<string,string>` | Required | The driver specific options used when creating the volume. | getOptions(): array | setOptions(array options): void |
| `scope` | [`string(ScopeEnum)`](../../doc/models/scope-enum.md) | Required | - | getScope(): string | setScope(string scope): void |
| `status` | `?array` | Optional | Low-level details about the volume, provided by the volume driver.<br>Details are returned as a map with key/value pairs:<br>`{"key":"value","key2":"value2"}`.<br><br>The `Status` field is optional, and is omitted if the volume driver<br>does not support this feature. | getStatus(): ?array | setStatus(?array status): void |
| `usageData` | `?array` | Optional | - | getUsageData(): ?array | setUsageData(?array usageData): void |

## Example

```php
use DockerLib\Models\Builders\VolumeBuilder;
use DockerLib\Models\ScopeEnum;
use DockerLib\ApiHelper;

$volume = VolumeBuilder::init(
    'Driver8',
    [
        'key0' => 'Labels8',
        'key1' => 'Labels9',
        'key2' => 'Labels0'
    ],
    'Mountpoint4',
    'Name4',
    [
        'key0' => 'Options0'
    ],
    ScopeEnum::LOCAL
)
    ->createdAt('CreatedAt6')
    ->status(
        [
            'key0' => ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'),
            'key1' => ApiHelper::deserialize('{"key1":"val1","key2":"val2"}')
        ]
    )
    ->usageData(ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

