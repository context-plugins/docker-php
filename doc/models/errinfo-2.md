
# Errinfo 2

## Structure

`Errinfo2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `apiCallDockerId` | `?string` | Optional | ID of docker user. | getApiCallDockerId(): ?string | setApiCallDockerId(?string apiCallDockerId): void |
| `apiCallName` | `?string` | Optional | Name of the API operation called. | getApiCallName(): ?string | setApiCallName(?string apiCallName): void |
| `apiCallStart` | `?string` | Optional | Date/time of call start. | getApiCallStart(): ?string | setApiCallStart(?string apiCallStart): void |
| `apiCallTxnid` | `?string` | Optional | Unique ID for this call. | getApiCallTxnid(): ?string | setApiCallTxnid(?string apiCallTxnid): void |

## Example

```php
use DockerLib\Models\Builders\Errinfo2Builder;

$errinfo2 = Errinfo2Builder::init()
    ->apiCallDockerId('api_call_docker_id4')
    ->apiCallName('api_call_name0')
    ->apiCallStart('api_call_start6')
    ->apiCallTxnid('api_call_txnid4')
    ->build();
```

