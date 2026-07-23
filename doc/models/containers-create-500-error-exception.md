
# Containers Create 500 Error Exception

## Structure

`ContainersCreate500ErrorException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `message` | `string` | Required | The error message. | getMessage(): string | setMessage(string message): void |

## Example

```php
try {
    // make the API call
} catch (ContainersCreate500ErrorException $exp) {
    echo 'Caught ContainersCreate500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught ApiException:', $exp;
}
```

