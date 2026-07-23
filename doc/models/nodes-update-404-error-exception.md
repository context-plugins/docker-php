
# Nodes Update 404 Error Exception

## Structure

`NodesUpdate404ErrorException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `message` | `string` | Required | The error message. | getMessage(): string | setMessage(string message): void |

## Example

```php
try {
    // make the API call
} catch (NodesUpdate404ErrorException $exp) {
    echo 'Caught NodesUpdate404ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught ApiException:', $exp;
}
```

