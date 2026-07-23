
# V2 Access Tokens 400 Error Exception

## Structure

`V2AccessTokens400ErrorException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `fields` | `?(string[])` | Optional | - | getFields(): ?array | setFields(?array fields): void |
| `text` | `?string` | Optional | - | getText(): ?string | setText(?string text): void |

## Example

```php
try {
    // make the API call
} catch (V2AccessTokens400ErrorException $exp) {
    echo 'Caught V2AccessTokens400ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught ApiException:', $exp;
}
```

