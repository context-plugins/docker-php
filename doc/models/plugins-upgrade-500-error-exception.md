
# Plugins Upgrade 500 Error Exception

## Structure

`PluginsUpgrade500ErrorException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `message` | `string` | Required | The error message. | getMessage(): string | setMessage(string message): void |

## Example

```php
try {
    // make the API call
} catch (PluginsUpgrade500ErrorException $exp) {
    echo 'Caught PluginsUpgrade500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught ApiException:', $exp;
}
```

