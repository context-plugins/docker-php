
# Task

## Structure

`Task`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `assignedGenericResources` | [`?(GenericResource[])`](../../doc/models/generic-resource.md) | Optional | User-defined resources can be either Integer resources (e.g, `SSD=3`) or String resources (e.g, `GPU=UUID1`) | getAssignedGenericResources(): ?array | setAssignedGenericResources(?array assignedGenericResources): void |
| `createdAt` | `?string` | Optional | - | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `desiredState` | [`?string(TaskStateEnum)`](../../doc/models/task-state-enum.md) | Optional | - | getDesiredState(): ?string | setDesiredState(?string desiredState): void |
| `iD` | `?string` | Optional | The ID of the task. | getID(): ?string | setID(?string iD): void |
| `labels` | `?array<string,string>` | Optional | User-defined key/value metadata. | getLabels(): ?array | setLabels(?array labels): void |
| `name` | `?string` | Optional | Name of the task. | getName(): ?string | setName(?string name): void |
| `nodeID` | `?string` | Optional | The ID of the node that this task is on. | getNodeID(): ?string | setNodeID(?string nodeID): void |
| `serviceID` | `?string` | Optional | The ID of the service this task is part of. | getServiceID(): ?string | setServiceID(?string serviceID): void |
| `slot` | `?int` | Optional | - | getSlot(): ?int | setSlot(?int slot): void |
| `spec` | [`?Spec5`](../../doc/models/spec-5.md) | Optional | - | getSpec(): ?Spec5 | setSpec(?Spec5 spec): void |
| `status` | [`?Status`](../../doc/models/status.md) | Optional | - | getStatus(): ?Status | setStatus(?Status status): void |
| `updatedAt` | `?string` | Optional | - | getUpdatedAt(): ?string | setUpdatedAt(?string updatedAt): void |
| `version` | [`?Version`](../../doc/models/version.md) | Optional | - | getVersion(): ?Version | setVersion(?Version version): void |

## Example

```php
use DockerLib\Models\Builders\TaskBuilder;
use DockerLib\Models\Builders\GenericResourceBuilder;
use DockerLib\Models\Builders\DiscreteResourceSpecBuilder;
use DockerLib\Models\Builders\NamedResourceSpecBuilder;
use DockerLib\Models\TaskStateEnum;
use DockerLib\Models\Builders\Spec5Builder;
use DockerLib\Models\Builders\ContainerSpec2Builder;
use DockerLib\Models\Builders\PlacementBuilder;
use DockerLib\Models\Builders\Resources2Builder;
use DockerLib\Models\Builders\LimitsBuilder;
use DockerLib\Models\Builders\RestartPolicy2Builder;
use DockerLib\Models\ConditionEnum;
use DockerLib\Models\Builders\StatusBuilder;
use DockerLib\Models\Builders\ContainerStatusBuilder;
use DockerLib\Models\Builders\VersionBuilder;

$task = TaskBuilder::init()
    ->assignedGenericResources(
        [
            GenericResourceBuilder::init()
                ->discreteResourceSpec(
                    DiscreteResourceSpecBuilder::init()
                        ->kind('SSD')
                        ->value(3)
                        ->build()
                )
                ->namedResourceSpec(
                    NamedResourceSpecBuilder::init()
                        ->kind('Kind8')
                        ->value('Value8')
                        ->build()
                )
                ->build(),
            GenericResourceBuilder::init()
                ->discreteResourceSpec(
                    DiscreteResourceSpecBuilder::init()
                        ->kind('Kind8')
                        ->value(98)
                        ->build()
                )
                ->namedResourceSpec(
                    NamedResourceSpecBuilder::init()
                        ->kind('GPU')
                        ->value('UUID1')
                        ->build()
                )
                ->build(),
            GenericResourceBuilder::init()
                ->discreteResourceSpec(
                    DiscreteResourceSpecBuilder::init()
                        ->kind('Kind8')
                        ->value(98)
                        ->build()
                )
                ->namedResourceSpec(
                    NamedResourceSpecBuilder::init()
                        ->kind('GPU')
                        ->value('UUID2')
                        ->build()
                )
                ->build()
        ]
    )
    ->createdAt('2016-06-07T21:07:31.171892745Z')
    ->desiredState(TaskStateEnum::RUNNING)
    ->iD('0kzzo1i0y4jz6027t0k7aezc7')
    ->labels(
        [
            'key0' => 'Labels2',
            'key1' => 'Labels3',
            'key2' => 'Labels4'
        ]
    )
    ->nodeID('60gvrl6tm78dmak4yl7srz94v')
    ->serviceID('9mnpnzenvg8p8tdbtq4wvbkcz')
    ->slot(1)
    ->spec(
        Spec5Builder::init()
            ->containerSpec(
                ContainerSpec2Builder::init()
                    ->image('redis')
                    ->build()
            )
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
    ->status(
        StatusBuilder::init()
            ->containerStatus(
                ContainerStatusBuilder::init()
                    ->containerID('e5d62702a1b48d01c3e02ca1e0212a250801fa8d67caca0b6f35919ebc12f035')
                    ->pID(677)
                    ->build()
            )
            ->message('started')
            ->state(TaskStateEnum::RUNNING)
            ->timestamp('2016-06-07T21:07:31.290032978Z')
            ->build()
    )
    ->updatedAt('2016-06-07T21:07:31.376370513Z')
    ->version(
        VersionBuilder::init()
            ->index(71)
            ->build()
    )
    ->build();
```

