
# Error Info

Context information for an error used for diagnostics.

## Structure

`ErrorInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `apiCallDockerId` | `?string` | Optional | ID of docker user. | getApiCallDockerId(): ?string | setApiCallDockerId(?string apiCallDockerId): void |
| `apiCallName` | `?string` | Optional | Name of the API operation called. | getApiCallName(): ?string | setApiCallName(?string apiCallName): void |
| `apiCallStart` | `?string` | Optional | Date/time of call start. | getApiCallStart(): ?string | setApiCallStart(?string apiCallStart): void |
| `apiCallTxnid` | `?string` | Optional | Unique ID for this call. | getApiCallTxnid(): ?string | setApiCallTxnid(?string apiCallTxnid): void |

## Example

```php
use DockerLib\Models\Builders\ErrorInfoBuilder;

$errorInfo = ErrorInfoBuilder::init()
    ->apiCallDockerId('api_call_docker_id6')
    ->apiCallName('api_call_name2')
    ->apiCallStart('api_call_start8')
    ->apiCallTxnid('api_call_txnid4')
    ->build();
```

