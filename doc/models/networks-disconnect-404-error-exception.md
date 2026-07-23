
# Networks Disconnect 404 Error Exception

## Structure

`NetworksDisconnect404ErrorException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `message` | `string` | Required | The error message. | getMessage(): string | setMessage(string message): void |

## Example

```php
try {
    // make the API call
} catch (NetworksDisconnect404ErrorException $exp) {
    echo 'Caught NetworksDisconnect404ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught ApiException:', $exp;
}
```

