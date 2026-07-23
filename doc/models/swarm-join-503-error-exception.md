
# Swarm Join 503 Error Exception

## Structure

`SwarmJoin503ErrorException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `message` | `string` | Required | The error message. | getMessage(): string | setMessage(string message): void |

## Example

```php
try {
    // make the API call
} catch (SwarmJoin503ErrorException $exp) {
    echo 'Caught SwarmJoin503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught ApiException:', $exp;
}
```

