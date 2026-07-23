
# Swarm Join Request

## Structure

`SwarmJoinRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `advertiseAddr` | `?string` | Optional | Externally reachable address advertised to other nodes. This can either be an address/port combination in the form `192.168.1.1:4567`, or an interface followed by a port number, like `eth0:4567`. If the port number is omitted, the port number from the listen address is used. If `AdvertiseAddr` is not specified, it will be automatically detected when possible. | getAdvertiseAddr(): ?string | setAdvertiseAddr(?string advertiseAddr): void |
| `dataPathAddr` | `?string` | Optional | Address or interface to use for data path traffic (format: `<ip\|interface>`), for example,  `192.168.1.1`,<br>or an interface, like `eth0`. If `DataPathAddr` is unspecified, the same address as `AdvertiseAddr`<br>is used.<br><br>The `DataPathAddr` specifies the address that global scope network drivers will publish towards other<br>nodes in order to reach the containers running on this node. Using this parameter it is possible to<br>separate the container data traffic from the management traffic of the cluster. | getDataPathAddr(): ?string | setDataPathAddr(?string dataPathAddr): void |
| `joinToken` | `?string` | Optional | Secret token for joining this swarm. | getJoinToken(): ?string | setJoinToken(?string joinToken): void |
| `listenAddr` | `?string` | Optional | Listen address used for inter-manager communication if the node gets promoted to manager, as well as determining the networking interface used for the VXLAN Tunnel Endpoint (VTEP). | getListenAddr(): ?string | setListenAddr(?string listenAddr): void |
| `remoteAddrs` | `?string` | Optional | Addresses of manager nodes already participating in the swarm. | getRemoteAddrs(): ?string | setRemoteAddrs(?string remoteAddrs): void |

## Example

```php
use DockerLib\Models\Builders\SwarmJoinRequestBuilder;

$swarmJoinRequest = SwarmJoinRequestBuilder::init()
    ->advertiseAddr('192.168.1.1:2377')
    ->dataPathAddr('DataPathAddr2')
    ->joinToken('SWMTKN-1-3pu6hszjas19xyp7ghgosyx9k8atbfcr8p2is99znpy26u2lkl-7p73s1dx5in4tatdymyhg9hu2')
    ->listenAddr('0.0.0.0:2377')
    ->remoteAddrs('["node1:2377"]')
    ->build();
```

