
# Networks Connect 500 Error Exception

## Structure

`NetworksConnect500ErrorException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `message` | `string` | Required | The error message. | getMessage(): string | setMessage(string message): void |

## Example

```php
try {
    // make the API call
} catch (NetworksConnect500ErrorException $exp) {
    echo 'Caught NetworksConnect500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught ApiException:', $exp;
}
```

