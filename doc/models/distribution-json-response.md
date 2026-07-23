
# Distribution Json Response

## Structure

`DistributionJsonResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `descriptor` | [`Descriptor1`](../../doc/models/descriptor-1.md) | Required | - | getDescriptor(): Descriptor1 | setDescriptor(Descriptor1 descriptor): void |
| `platforms` | [`Platform1[]`](../../doc/models/platform-1.md) | Required | An array containing all platforms supported by the image | getPlatforms(): array | setPlatforms(array platforms): void |

## Example

```php
use DockerLib\Models\Builders\DistributionJsonResponseBuilder;
use DockerLib\Models\Builders\Descriptor1Builder;
use DockerLib\Models\Builders\Platform1Builder;

$distributionJsonResponse = DistributionJsonResponseBuilder::init(
    Descriptor1Builder::init()
        ->digest('Digest4')
        ->mediaType('MediaType0')
        ->size(240)
        ->uRLs(
            [
                'URLs5',
                'URLs6',
                'URLs7'
            ]
        )
        ->build(),
    [
        Platform1Builder::init()
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
            ->build()
    ]
)->build();
```

