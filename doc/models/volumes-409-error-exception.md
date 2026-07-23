
# Volumes 409 Error Exception

## Structure

`Volumes409ErrorException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `message` | `string` | Required | The error message. | getMessage(): string | setMessage(string message): void |

## Example

```php
try {
    // make the API call
} catch (Volumes409ErrorException $exp) {
    echo 'Caught Volumes409ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught ApiException:', $exp;
}
```

