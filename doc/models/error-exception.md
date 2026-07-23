
# Error Exception

## Structure

`ErrorException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `detail` | `?string` | Optional | - | getDetail(): ?string | setDetail(?string detail): void |
| `message` | `?string` | Optional | - | getMessage(): ?string | setMessage(?string message): void |

## Example

```php
try {
    // make the API call
} catch (ErrorException $exp) {
    echo 'Caught ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught ApiException:', $exp;
}
```

