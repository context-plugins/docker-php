
# Details

## Structure

`Details`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error1[])`](../../doc/models/error-1.md) | Optional | Errors from validating delete request. These cannot be ignored. | getErrors(): ?array | setErrors(?array errors): void |
| `warnings` | [`?(Warning1[])`](../../doc/models/warning-1.md) | Optional | Warnings that can be ignored.<br><br>These warnings include:<br><br>- is_active: warning when attempting to delete an image that is marked as<br>  active.<br>- current_tag: warning when attempting to delete an image that has one or<br>  more current tags in the repository.<br><br>Warnings can be copied from the response to the request. | getWarnings(): ?array | setWarnings(?array warnings): void |

## Example

```php
use DockerLib\Models\Builders\DetailsBuilder;
use DockerLib\Models\Builders\Error1Builder;
use DockerLib\Models\Error2Enum;
use DockerLib\Models\Builders\Warning1Builder;
use DockerLib\Models\Warning2Enum;

$details = DetailsBuilder::init()
    ->errors(
        [
            Error1Builder::init()
                ->digest('digest6')
                ->error(Error2Enum::CHILD_MANIFEST)
                ->repository('repository0')
                ->build(),
            Error1Builder::init()
                ->digest('digest6')
                ->error(Error2Enum::CHILD_MANIFEST)
                ->repository('repository0')
                ->build()
        ]
    )
    ->warnings(
        [
            Warning1Builder::init()
                ->digest('digest0')
                ->repository('repository4')
                ->tags(
                    [
                        'tags9',
                        'tags0'
                    ]
                )
                ->warning(Warning2Enum::IS_ACTIVE)
                ->build(),
            Warning1Builder::init()
                ->digest('digest0')
                ->repository('repository4')
                ->tags(
                    [
                        'tags9',
                        'tags0'
                    ]
                )
                ->warning(Warning2Enum::IS_ACTIVE)
                ->build(),
            Warning1Builder::init()
                ->digest('digest0')
                ->repository('repository4')
                ->tags(
                    [
                        'tags9',
                        'tags0'
                    ]
                )
                ->warning(Warning2Enum::IS_ACTIVE)
                ->build()
        ]
    )
    ->build();
```

