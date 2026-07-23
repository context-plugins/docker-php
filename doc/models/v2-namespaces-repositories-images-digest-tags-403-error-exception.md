
# V2 Namespaces Repositories Images Digest Tags 403 Error Exception

## Structure

`V2NamespacesRepositoriesImagesDigestTags403ErrorException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errinfo` | [`?Errinfo2`](../../doc/models/errinfo-2.md) | Optional | - | getErrinfo(): ?Errinfo2 | setErrinfo(?Errinfo2 errinfo): void |
| `message` | `?string` | Optional | The error message. | getMessage(): ?string | setMessage(?string message): void |
| `txnid` | `?string` | Optional | Unique ID for this call. | getTxnid(): ?string | setTxnid(?string txnid): void |

## Example

```php
try {
    // make the API call
} catch (V2NamespacesRepositoriesImagesDigestTags403ErrorException $exp) {
    echo 'Caught V2NamespacesRepositoriesImagesDigestTags403ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught ApiException:', $exp;
}
```

