
# V2 Users Login 401 Error Exception

## Structure

`V2UsersLogin401ErrorException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `detail` | `string` | Required | Description of the error. | getDetail(): string | setDetail(string detail): void |
| `login2faToken` | `?string` | Optional | Short time lived token to be used on `/v2/users/2fa-login` to complete the authentication. This field is present only if 2FA is enabled. | getLogin2faToken(): ?string | setLogin2faToken(?string login2faToken): void |

## Example

```php
try {
    // make the API call
} catch (V2UsersLogin401ErrorException $exp) {
    echo 'Caught V2UsersLogin401ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught ApiException:', $exp;
}
```

