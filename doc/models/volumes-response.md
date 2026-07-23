
# Volumes Response

## Structure

`VolumesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `volumes` | [`Volume[]`](../../doc/models/volume.md) | Required | List of volumes | getVolumes(): array | setVolumes(array volumes): void |
| `warnings` | `string[]` | Required | Warnings that occurred when fetching the list of volumes | getWarnings(): array | setWarnings(array warnings): void |

## Example

```php
use DockerLib\Models\Builders\VolumesResponseBuilder;
use DockerLib\Models\Builders\VolumeBuilder;
use DockerLib\Models\ScopeEnum;
use DockerLib\ApiHelper;

$volumesResponse = VolumesResponseBuilder::init(
    [
        VolumeBuilder::init(
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
            ->build()
    ],
    [
        'Warnings9',
        'Warnings0'
    ]
)->build();
```

