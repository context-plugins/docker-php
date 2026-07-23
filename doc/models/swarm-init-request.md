
# Swarm Init Request

## Structure

`SwarmInitRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `advertiseAddr` | `?string` | Optional | Externally reachable address advertised to other nodes. This can either be an address/port combination in the form `192.168.1.1:4567`, or an interface followed by a port number, like `eth0:4567`. If the port number is omitted, the port number from the listen address is used. If `AdvertiseAddr` is not specified, it will be automatically detected when possible. | getAdvertiseAddr(): ?string | setAdvertiseAddr(?string advertiseAddr): void |
| `dataPathAddr` | `?string` | Optional | Address or interface to use for data path traffic (format: `<ip\|interface>`), for example,  `192.168.1.1`,<br>or an interface, like `eth0`. If `DataPathAddr` is unspecified, the same address as `AdvertiseAddr`<br>is used.<br><br>The `DataPathAddr` specifies the address that global scope network drivers will publish towards other<br>nodes in order to reach the containers running on this node. Using this parameter it is possible to<br>separate the container data traffic from the management traffic of the cluster. | getDataPathAddr(): ?string | setDataPathAddr(?string dataPathAddr): void |
| `forceNewCluster` | `?bool` | Optional | Force creation of a new swarm. | getForceNewCluster(): ?bool | setForceNewCluster(?bool forceNewCluster): void |
| `listenAddr` | `?string` | Optional | Listen address used for inter-manager communication, as well as determining the networking interface used for the VXLAN Tunnel Endpoint (VTEP). This can either be an address/port combination in the form `192.168.1.1:4567`, or an interface followed by a port number, like `eth0:4567`. If the port number is omitted, the default swarm listening port is used. | getListenAddr(): ?string | setListenAddr(?string listenAddr): void |
| `spec` | [`?Spec`](../../doc/models/spec.md) | Optional | - | getSpec(): ?Spec | setSpec(?Spec spec): void |

## Example

```php
use DockerLib\Models\Builders\SwarmInitRequestBuilder;
use DockerLib\Models\Builders\SpecBuilder;
use DockerLib\ApiHelper;
use DockerLib\Models\Builders\EncryptionConfig2Builder;
use DockerLib\Models\Builders\Raft2Builder;

$swarmInitRequest = SwarmInitRequestBuilder::init()
    ->advertiseAddr('192.168.1.1:2377')
    ->dataPathAddr('DataPathAddr4')
    ->forceNewCluster(false)
    ->listenAddr('0.0.0.0:2377')
    ->spec(
        SpecBuilder::init()
            ->cAConfig(ApiHelper::deserialize('{}'))
            ->dispatcher(ApiHelper::deserialize('{}'))
            ->encryptionConfig(
                EncryptionConfig2Builder::init()
                    ->autoLockManagers(false)
                    ->build()
            )
            ->labels(
                [
                    'key0' => 'Labels0',
                    'key1' => 'Labels1',
                    'key2' => 'Labels2'
                ]
            )
            ->name('Name2')
            ->orchestration(ApiHelper::deserialize('{}'))
            ->raft(
                Raft2Builder::init()->build()
            )->build()
    )->build();
```

