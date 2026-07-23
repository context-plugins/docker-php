
# Service

## Structure

`Service`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `createdAt` | `?string` | Optional | - | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `endpoint` | [`?Endpoint`](../../doc/models/endpoint.md) | Optional | - | getEndpoint(): ?Endpoint | setEndpoint(?Endpoint endpoint): void |
| `iD` | `?string` | Optional | - | getID(): ?string | setID(?string iD): void |
| `spec` | [`?ServicesCreateRequest`](../../doc/models/services-create-request.md) | Optional | - | getSpec(): ?ServicesCreateRequest | setSpec(?ServicesCreateRequest spec): void |
| `updateStatus` | [`?UpdateStatus2`](../../doc/models/update-status-2.md) | Optional | - | getUpdateStatus(): ?UpdateStatus2 | setUpdateStatus(?UpdateStatus2 updateStatus): void |
| `updatedAt` | `?string` | Optional | - | getUpdatedAt(): ?string | setUpdatedAt(?string updatedAt): void |
| `version` | [`?Version`](../../doc/models/version.md) | Optional | - | getVersion(): ?Version | setVersion(?Version version): void |

## Example

```php
use DockerLib\Models\Builders\ServiceBuilder;
use DockerLib\Models\Builders\EndpointBuilder;
use DockerLib\Models\Builders\EndpointPortConfigBuilder;
use DockerLib\Models\Protocol1Enum;
use DockerLib\Models\Builders\Spec2Builder;
use DockerLib\Models\ModeEnum;
use DockerLib\Models\Builders\VirtualIPBuilder;
use DockerLib\Models\Builders\ServicesCreateRequestBuilder;
use DockerLib\Models\Builders\EndpointSpec1Builder;
use DockerLib\Models\Builders\Mode3Builder;
use DockerLib\ApiHelper;
use DockerLib\Models\Builders\ReplicatedBuilder;
use DockerLib\Models\Builders\Network2Builder;
use DockerLib\Models\Builders\RollbackConfig2Builder;
use DockerLib\Models\FailureActionEnum;
use DockerLib\Models\Builders\TaskTemplateBuilder;
use DockerLib\Models\Builders\ContainerSpec2Builder;
use DockerLib\Models\Builders\PlacementBuilder;
use DockerLib\Models\Builders\Resources2Builder;
use DockerLib\Models\Builders\LimitsBuilder;
use DockerLib\Models\Builders\RestartPolicy2Builder;
use DockerLib\Models\ConditionEnum;
use DockerLib\Models\Builders\UpdateConfig1Builder;
use DockerLib\Models\FailureAction1Enum;
use DockerLib\Models\Builders\UpdateStatus2Builder;
use DockerLib\Models\StateEnum;
use DockerLib\Models\Builders\VersionBuilder;

$service = ServiceBuilder::init()
    ->createdAt('2016-06-07T21:05:51.880065305Z')
    ->endpoint(
        EndpointBuilder::init()
            ->ports(
                [
                    EndpointPortConfigBuilder::init()
                        ->name('Name6')
                        ->protocol(Protocol1Enum::TCP)
                        ->publishedPort(30001)
                        ->targetPort(6379)
                        ->build()
                ]
            )
            ->spec(
                Spec2Builder::init()
                    ->mode(ModeEnum::VIP)
                    ->ports(
                        [
                            EndpointPortConfigBuilder::init()
                                ->name('Name6')
                                ->protocol(Protocol1Enum::TCP)
                                ->publishedPort(30001)
                                ->targetPort(6379)
                                ->build()
                        ]
                    )
                    ->build()
            )
            ->virtualIPs(
                [
                    VirtualIPBuilder::init()
                        ->addr('10.255.0.2/16')
                        ->networkID('4qvuz4ko70xaltuqbt8956gd1')
                        ->build(),
                    VirtualIPBuilder::init()
                        ->addr('10.255.0.3/16')
                        ->networkID('4qvuz4ko70xaltuqbt8956gd1')
                        ->build()
                ]
            )
            ->build()
    )
    ->iD('9mnpnzenvg8p8tdbtq4wvbkcz')
    ->spec(
        ServicesCreateRequestBuilder::init()
            ->endpointSpec(
                EndpointSpec1Builder::init()
                    ->mode(ModeEnum::VIP)
                    ->ports(
                        [
                            EndpointPortConfigBuilder::init()
                                ->name('Name6')
                                ->protocol(Protocol1Enum::TCP)
                                ->publishedPort(30001)
                                ->targetPort(6379)
                                ->build()
                        ]
                    )
                    ->build()
            )
            ->labels(
                [
                    'key0' => 'Labels0',
                    'key1' => 'Labels1',
                    'key2' => 'Labels2'
                ]
            )
            ->mode(
                Mode3Builder::init()
                    ->global(ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->replicated(
                        ReplicatedBuilder::init()
                            ->replicas(1)
                            ->build()
                    )
                    ->build()
            )
            ->name('hopeful_cori')
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
                        ->build(),
                    Network2Builder::init()
                        ->aliases(
                            [
                                'Aliases6',
                                'Aliases5',
                                'Aliases4'
                            ]
                        )
                        ->target('Target8')
                        ->build(),
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
            ->rollbackConfig(
                RollbackConfig2Builder::init()
                    ->delay(1000000000)
                    ->failureAction(FailureActionEnum::PAUSE)
                    ->maxFailureRatio(0.15)
                    ->monitor(15000000000)
                    ->parallelism(1)
                    ->build()
            )
            ->taskTemplate(
                TaskTemplateBuilder::init()
                    ->containerSpec(
                        ContainerSpec2Builder::init()
                            ->image('redis')
                            ->build()
                    )
                    ->forceUpdate(0)
                    ->placement(
                        PlacementBuilder::init()->build()
                    )
                    ->resources(
                        Resources2Builder::init()
                            ->limits(
                                LimitsBuilder::init()->build()
                            )->build()
                    )
                    ->restartPolicy(
                        RestartPolicy2Builder::init()
                            ->condition(ConditionEnum::ANY)
                            ->maxAttempts(0)
                            ->build()
                    )
                    ->build()
            )
            ->updateConfig(
                UpdateConfig1Builder::init()
                    ->delay(1000000000)
                    ->failureAction(FailureAction1Enum::PAUSE)
                    ->maxFailureRatio(0.15)
                    ->monitor(15000000000)
                    ->parallelism(1)
                    ->build()
            )
            ->build()
    )
    ->updateStatus(
        UpdateStatus2Builder::init()
            ->completedAt('CompletedAt0')
            ->message('Message0')
            ->startedAt('StartedAt8')
            ->state(StateEnum::UPDATING)
            ->build()
    )
    ->updatedAt('2016-06-07T21:07:29.962229872Z')
    ->version(
        VersionBuilder::init()
            ->index(19)
            ->build()
    )
    ->build();
```

