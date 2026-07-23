
# Host Config 2

## Structure

`HostConfig2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `networkMode` | `?string` | Optional | - | getNetworkMode(): ?string | setNetworkMode(?string networkMode): void |

## Example

```php
use DockerLib\Models\Builders\HostConfig2Builder;

$hostConfig2 = HostConfig2Builder::init()
    ->networkMode('NetworkMode6')
    ->build();
```

