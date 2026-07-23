
# Networks Disconnect Request

## Structure

`NetworksDisconnectRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `container` | `?string` | Optional | The ID or name of the container to disconnect from the network. | getContainer(): ?string | setContainer(?string container): void |
| `force` | `?bool` | Optional | Force the container to disconnect from the network. | getForce(): ?bool | setForce(?bool force): void |

## Example

```php
use DockerLib\Models\Builders\NetworksDisconnectRequestBuilder;

$networksDisconnectRequest = NetworksDisconnectRequestBuilder::init()
    ->container('Container0')
    ->force(false)
    ->build();
```

