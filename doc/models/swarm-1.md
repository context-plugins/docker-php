
# Swarm 1

## Structure

`Swarm1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cluster` | `?array` | Optional | - | getCluster(): ?array | setCluster(?array cluster): void |
| `controlAvailable` | `?bool` | Optional | **Default**: `false` | getControlAvailable(): ?bool | setControlAvailable(?bool controlAvailable): void |
| `error` | `?string` | Optional | - | getError(): ?string | setError(?string error): void |
| `localNodeState` | [`?string(LocalNodeStateEnum)`](../../doc/models/local-node-state-enum.md) | Optional | - | getLocalNodeState(): ?string | setLocalNodeState(?string localNodeState): void |
| `managers` | `?int` | Optional | Total number of managers in the swarm. | getManagers(): ?int | setManagers(?int managers): void |
| `nodeAddr` | `?string` | Optional | IP address at which this node can be reached by other nodes in the<br>swarm. | getNodeAddr(): ?string | setNodeAddr(?string nodeAddr): void |
| `nodeID` | `?string` | Optional | Unique identifier of for this node in the swarm. | getNodeID(): ?string | setNodeID(?string nodeID): void |
| `nodes` | `?int` | Optional | Total number of nodes in the swarm. | getNodes(): ?int | setNodes(?int nodes): void |
| `remoteManagers` | [`?(PeerNode[])`](../../doc/models/peer-node.md) | Optional | List of ID's and addresses of other managers in the swarm. | getRemoteManagers(): ?array | setRemoteManagers(?array remoteManagers): void |

## Example

```php
use DockerLib\Models\Builders\Swarm1Builder;
use DockerLib\ApiHelper;
use DockerLib\Models\LocalNodeStateEnum;
use DockerLib\Models\Builders\PeerNodeBuilder;

$swarm1 = Swarm1Builder::init()
    ->cluster(ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->controlAvailable(true)
    ->error('Error6')
    ->localNodeState(LocalNodeStateEnum::ERROR)
    ->managers(3)
    ->nodeAddr('10.0.0.46')
    ->nodeID('k67qz4598weg5unwwffg6z1m1')
    ->nodes(4)
    ->remoteManagers(
        [
            PeerNodeBuilder::init()
                ->addr('10.0.0.158:2377')
                ->nodeID('71izy0goik036k48jg985xnds')
                ->build(),
            PeerNodeBuilder::init()
                ->addr('10.0.0.159:2377')
                ->nodeID('79y6h1o4gv8n120drcprv5nmc')
                ->build(),
            PeerNodeBuilder::init()
                ->addr('10.0.0.46:2377')
                ->nodeID('k67qz4598weg5unwwffg6z1m1')
                ->build()
        ]
    )
    ->build();
```

