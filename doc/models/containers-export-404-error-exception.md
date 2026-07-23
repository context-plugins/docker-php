
# Containers Export 404 Error Exception

## Structure

`ContainersExport404ErrorException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `message` | `string` | Required | - | getMessage(): string | setMessage(string message): void |

## Example

```php
try {
    // make the API call
} catch (ContainersExport404ErrorException $exp) {
    echo 'Caught ContainersExport404ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught ApiException:', $exp;
}
```

