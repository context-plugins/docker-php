
# Platform 1

## Structure

`Platform1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `architecture` | `?string` | Optional | - | getArchitecture(): ?string | setArchitecture(?string architecture): void |
| `features` | `?(string[])` | Optional | - | getFeatures(): ?array | setFeatures(?array features): void |
| `oS` | `?string` | Optional | - | getOS(): ?string | setOS(?string oS): void |
| `oSFeatures` | `?(string[])` | Optional | - | getOSFeatures(): ?array | setOSFeatures(?array oSFeatures): void |
| `oSVersion` | `?string` | Optional | - | getOSVersion(): ?string | setOSVersion(?string oSVersion): void |
| `variant` | `?string` | Optional | - | getVariant(): ?string | setVariant(?string variant): void |

## Example

```php
use DockerLib\Models\Builders\Platform1Builder;

$platform1 = Platform1Builder::init()
    ->architecture('Architecture2')
    ->features(
        [
            'Features4'
        ]
    )
    ->oS('OS0')
    ->oSFeatures(
        [
            'OSFeatures0',
            'OSFeatures1',
            'OSFeatures2'
        ]
    )
    ->oSVersion('OSVersion4')
    ->build();
```

