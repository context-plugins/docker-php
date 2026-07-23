
# Error Response 1

Represents an error.

## Structure

`ErrorResponse1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errinfo` | [`?Errinfo2`](../../doc/models/errinfo-2.md) | Optional | - | getErrinfo(): ?Errinfo2 | setErrinfo(?Errinfo2 errinfo): void |
| `message` | `?string` | Optional | The error message. | getMessage(): ?string | setMessage(?string message): void |
| `txnid` | `?string` | Optional | Unique ID for this call. | getTxnid(): ?string | setTxnid(?string txnid): void |

## Example

```php
use DockerLib\Models\Builders\ErrorResponse1Builder;
use DockerLib\Models\Builders\Errinfo2Builder;

$errorResponse1 = ErrorResponse1Builder::init()
    ->errinfo(
        Errinfo2Builder::init()
            ->apiCallDockerId('api_call_docker_id6')
            ->apiCallName('api_call_name2')
            ->apiCallStart('api_call_start8')
            ->apiCallTxnid('api_call_txnid4')
            ->build()
    )
    ->message('message4')
    ->txnid('txnid0')
    ->build();
```

