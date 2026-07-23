
# Containers Attach Ws 400 Error Exception

## Structure

`ContainersAttachWs400ErrorException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `message` | `string` | Required | The error message. | getMessage(): string | setMessage(string message): void |

## Example

```php
try {
    // make the API call
} catch (ContainersAttachWs400ErrorException $exp) {
    echo 'Caught ContainersAttachWs400ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught ApiException:', $exp;
}
```

