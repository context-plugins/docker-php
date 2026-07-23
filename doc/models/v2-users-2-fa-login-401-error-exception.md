
# V2 Users 2 Fa Login 401 Error Exception

## Structure

`V2Users2faLogin401ErrorException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `detail` | `?string` | Optional | Description of the error. | getDetail(): ?string | setDetail(?string detail): void |

## Example

```php
try {
    // make the API call
} catch (V2Users2faLogin401ErrorException $exp) {
    echo 'Caught V2Users2faLogin401ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught ApiException:', $exp;
}
```

