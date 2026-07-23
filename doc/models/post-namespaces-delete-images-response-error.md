
# Post Namespaces Delete Images Response Error

Deletion not possible.

## Structure

`PostNamespacesDeleteImagesResponseError`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errinfo` | [`?Errinfo`](../../doc/models/errinfo.md) | Optional | - | getErrinfo(): ?Errinfo | setErrinfo(?Errinfo errinfo): void |
| `message` | `?string` | Optional | The error message. | getMessage(): ?string | setMessage(?string message): void |
| `txnid` | `?string` | Optional | Unique ID for this call. | getTxnid(): ?string | setTxnid(?string txnid): void |

## Example

```php
use DockerLib\Models\Builders\PostNamespacesDeleteImagesResponseErrorBuilder;
use DockerLib\Models\Builders\ErrinfoBuilder;
use DockerLib\Models\Builders\DetailsBuilder;
use DockerLib\Models\Builders\Error1Builder;
use DockerLib\Models\Error2Enum;
use DockerLib\Models\Builders\Warning1Builder;
use DockerLib\Models\Warning2Enum;

$postNamespacesDeleteImagesResponseError = PostNamespacesDeleteImagesResponseErrorBuilder::init()
    ->errinfo(
        ErrinfoBuilder::init()
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
            ->build()
    )
    ->message('message8')
    ->txnid('txnid4')
    ->build();
```

