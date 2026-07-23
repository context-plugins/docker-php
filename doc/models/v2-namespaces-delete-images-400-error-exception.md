
# V2 Namespaces Delete Images 400 Error Exception

## Structure

`V2NamespacesDeleteImages400ErrorException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errinfo` | [`?Errinfo`](../../doc/models/errinfo.md) | Optional | - | getErrinfo(): ?Errinfo | setErrinfo(?Errinfo errinfo): void |
| `message` | `?string` | Optional | The error message. | getMessage(): ?string | setMessage(?string message): void |
| `txnid` | `?string` | Optional | Unique ID for this call. | getTxnid(): ?string | setTxnid(?string txnid): void |

## Example

```php
try {
    // make the API call
} catch (V2NamespacesDeleteImages400ErrorException $exp) {
    echo 'Caught V2NamespacesDeleteImages400ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught ApiException:', $exp;
}
```

