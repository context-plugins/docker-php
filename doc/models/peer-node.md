
# Peer Node

Represents a peer-node in the swarm

## Structure

`PeerNode`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `addr` | `?string` | Optional | IP address and ports at which this node can be reached. | getAddr(): ?string | setAddr(?string addr): void |
| `nodeID` | `?string` | Optional | Unique identifier of for this node in the swarm. | getNodeID(): ?string | setNodeID(?string nodeID): void |

## Example

```php
use DockerLib\Models\Builders\PeerNodeBuilder;

$peerNode = PeerNodeBuilder::init()
    ->addr('Addr6')
    ->nodeID('NodeID8')
    ->build();
```

