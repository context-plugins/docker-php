
# Image 1

## Structure

`Image1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `architecture` | `?string` | Optional | CPU architecture | getArchitecture(): ?string | setArchitecture(?string architecture): void |
| `digest` | `?string` | Optional | image digest | getDigest(): ?string | setDigest(?string digest): void |
| `features` | `?string` | Optional | CPU features | getFeatures(): ?string | setFeatures(?string features): void |
| `lastPulled` | `?string` | Optional | datetime of last pull | getLastPulled(): ?string | setLastPulled(?string lastPulled): void |
| `lastPushed` | `?string` | Optional | datetime of last push | getLastPushed(): ?string | setLastPushed(?string lastPushed): void |
| `layers` | [`?(Layer[])`](../../doc/models/layer.md) | Optional | - | getLayers(): ?array | setLayers(?array layers): void |
| `os` | `?string` | Optional | operating system | getOs(): ?string | setOs(?string os): void |
| `osFeatures` | `?string` | Optional | OS features | getOsFeatures(): ?string | setOsFeatures(?string osFeatures): void |
| `osVersion` | `?string` | Optional | OS version | getOsVersion(): ?string | setOsVersion(?string osVersion): void |
| `size` | `?int` | Optional | size of the image | getSize(): ?int | setSize(?int size): void |
| `status` | [`?string(Status11Enum)`](../../doc/models/status-11-enum.md) | Optional | - | getStatus(): ?string | setStatus(?string status): void |
| `variant` | `?string` | Optional | CPU variant | getVariant(): ?string | setVariant(?string variant): void |

## Example

```php
use DockerLib\Models\Builders\Image1Builder;

$image1 = Image1Builder::init()
    ->architecture('architecture6')
    ->digest('digest4')
    ->features('features2')
    ->lastPulled('2021-01-05T21:06:53.506400Z')
    ->lastPushed('2021-01-05T21:06:53.506400Z')
    ->build();
```

