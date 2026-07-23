
# Swarm Unlockkey 503 Error Exception

## Structure

`SwarmUnlockkey503ErrorException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `message` | `string` | Required | The error message. | getMessage(): string | setMessage(string message): void |

## Example

```php
try {
    // make the API call
} catch (SwarmUnlockkey503ErrorException $exp) {
    echo 'Caught SwarmUnlockkey503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught ApiException:', $exp;
}
```

