
# Containers Archive 404 Error 2 Exception

## Structure

`ContainersArchive404Error2Exception`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `message` | `string` | Required | The error message. | getMessage(): string | setMessage(string message): void |

## Example

```php
try {
    // make the API call
} catch (ContainersArchive404Error2Exception $exp) {
    echo 'Caught ContainersArchive404Error2Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught ApiException:', $exp;
}
```

