
# Errinfo

## Structure

`Errinfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `apiCallDockerId` | `?string` | Optional | ID of docker user. | getApiCallDockerId(): ?string | setApiCallDockerId(?string apiCallDockerId): void |
| `apiCallName` | `?string` | Optional | Name of the API operation called. | getApiCallName(): ?string | setApiCallName(?string apiCallName): void |
| `apiCallStart` | `?string` | Optional | Date/time of call start. | getApiCallStart(): ?string | setApiCallStart(?string apiCallStart): void |
| `apiCallTxnid` | `?string` | Optional | Unique ID for this call. | getApiCallTxnid(): ?string | setApiCallTxnid(?string apiCallTxnid): void |
| `details` | [`?Details`](../../doc/models/details.md) | Optional | - | getDetails(): ?Details | setDetails(?Details details): void |
| `type` | `?string` | Optional | Type of error. | getType(): ?string | setType(?string type): void |

## Example

```php
use DockerLib\Models\Builders\ErrinfoBuilder;
use DockerLib\Models\Builders\DetailsBuilder;
use DockerLib\Models\Builders\Error1Builder;
use DockerLib\Models\Error2Enum;
use DockerLib\Models\Builders\Warning1Builder;
use DockerLib\Models\Warning2Enum;

$errinfo = ErrinfoBuilder::init()
    ->apiCallDockerId('api_call_docker_id6')
    ->apiCallName('api_call_name2')
    ->apiCallStart('api_call_start8')
    ->apiCallTxnid('api_call_txnid4')
    ->details(
        DetailsBuilder::init()
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
            ->build()
    )
    ->type('validation')
    ->build();
```

