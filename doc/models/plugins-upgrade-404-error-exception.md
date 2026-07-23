
# Plugins Upgrade 404 Error Exception

## Structure

`PluginsUpgrade404ErrorException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `message` | `string` | Required | The error message. | getMessage(): string | setMessage(string message): void |

## Example

```php
try {
    // make the API call
} catch (PluginsUpgrade404ErrorException $exp) {
    echo 'Caught PluginsUpgrade404ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught ApiException:', $exp;
}
```

