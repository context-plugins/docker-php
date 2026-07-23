
# Scim Bad Request 1 Exception

## Structure

`ScimBadRequest1Exception`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `detail` | `?string` | Optional | Details about why the request failed. | getDetail(): ?string | setDetail(?string detail): void |
| `schemas` | `?(string[])` | Optional | - | getSchemas(): ?array | setSchemas(?array schemas): void |
| `status` | `?string` | Optional | The status code for the response in string format. | getStatus(): ?string | setStatus(?string status): void |
| `scimType` | `?string` | Optional | Some types of errors will return this per the specification. | getScimType(): ?string | setScimType(?string scimType): void |

## Example

```php
try {
    // make the API call
} catch (ScimBadRequest1Exception $exp) {
    echo 'Caught ScimBadRequest1Exception:', $exp;
} catch (ApiException $exp) {
    echo 'Caught ApiException:', $exp;
}
```

