
# Containers Archive 404 Error Exception

## Structure

`ContainersArchive404ErrorException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `message` | `string` | Required | - | getMessage(): string | setMessage(string message): void |

## Example

```php
try {
    // make the API call
} catch (ContainersArchive404ErrorException $exp) {
    echo 'Caught ContainersArchive404ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught ApiException:', $exp;
}
```

