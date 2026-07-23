
# Services Update Request

## Structure

`ServicesUpdateRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `endpointSpec` | [`?EndpointSpec1`](../../doc/models/endpoint-spec-1.md) | Optional | - | getEndpointSpec(): ?EndpointSpec1 | setEndpointSpec(?EndpointSpec1 endpointSpec): void |
| `labels` | `?array<string,string>` | Optional | User-defined key/value metadata. | getLabels(): ?array | setLabels(?array labels): void |
| `mode` | [`?Mode3`](../../doc/models/mode-3.md) | Optional | - | getMode(): ?Mode3 | setMode(?Mode3 mode): void |
| `name` | `?string` | Optional | Name of the service. | getName(): ?string | setName(?string name): void |
| `networks` | [`?(Network2[])`](../../doc/models/network-2.md) | Optional | Array of network names or IDs to attach the service to. | getNetworks(): ?array | setNetworks(?array networks): void |
| `rollbackConfig` | [`?RollbackConfig2`](../../doc/models/rollback-config-2.md) | Optional | - | getRollbackConfig(): ?RollbackConfig2 | setRollbackConfig(?RollbackConfig2 rollbackConfig): void |
| `taskTemplate` | [`?TaskTemplate`](../../doc/models/task-template.md) | Optional | - | getTaskTemplate(): ?TaskTemplate | setTaskTemplate(?TaskTemplate taskTemplate): void |
| `updateConfig` | [`?UpdateConfig1`](../../doc/models/update-config-1.md) | Optional | - | getUpdateConfig(): ?UpdateConfig1 | setUpdateConfig(?UpdateConfig1 updateConfig): void |

## Example

```php
use DockerLib\Models\Builders\ServicesUpdateRequestBuilder;
use DockerLib\Models\Builders\EndpointSpec1Builder;
use DockerLib\Models\ModeEnum;
use DockerLib\Models\Builders\EndpointPortConfigBuilder;
use DockerLib\Models\Protocol1Enum;
use DockerLib\Models\Builders\Mode3Builder;
use DockerLib\ApiHelper;
use DockerLib\Models\Builders\ReplicatedBuilder;
use DockerLib\Models\Builders\Network2Builder;

$servicesUpdateRequest = ServicesUpdateRequestBuilder::init()
    ->endpointSpec(
        EndpointSpec1Builder::init()
            ->mode(ModeEnum::VIP)
            ->ports(
                [
                    EndpointPortConfigBuilder::init()
                        ->name('Name6')
                        ->protocol(Protocol1Enum::TCP)
                        ->publishedPort(40)
                        ->targetPort(114)
                        ->build(),
                    EndpointPortConfigBuilder::init()
                        ->name('Name6')
                        ->protocol(Protocol1Enum::TCP)
                        ->publishedPort(40)
                        ->targetPort(114)
                        ->build(),
                    EndpointPortConfigBuilder::init()
                        ->name('Name6')
                        ->protocol(Protocol1Enum::TCP)
                        ->publishedPort(40)
                        ->targetPort(114)
                        ->build()
                ]
            )
            ->build()
    )
    ->labels(
        [
            'key0' => 'Labels2'
        ]
    )
    ->mode(
        Mode3Builder::init()
            ->global(ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->replicated(
                ReplicatedBuilder::init()
                    ->replicas(34)
                    ->build()
            )
            ->build()
    )
    ->name('Name4')
    ->networks(
        [
            Network2Builder::init()
                ->aliases(
                    [
                        'Aliases6',
                        'Aliases5',
                        'Aliases4'
                    ]
                )
                ->target('Target8')
                ->build()
        ]
    )
    ->build();
```

