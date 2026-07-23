
# Scim Error Exception

## Structure

`ScimErrorException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `detail` | `?string` | Optional | Details about why the request failed. | getDetail(): ?string | setDetail(?string detail): void |
| `schemas` | `?(string[])` | Optional | - | getSchemas(): ?array | setSchemas(?array schemas): void |
| `status` | `?string` | Optional | The status code for the response in string format. | getStatus(): ?string | setStatus(?string status): void |

## Example

```php
try {
    // make the API call
} catch (ScimErrorException $exp) {
    echo 'Caught ScimErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught ApiException:', $exp;
}
```

