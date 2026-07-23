
# Rpc Status Exception

## Structure

`RpcStatusException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `code` | `?int` | Optional | - | getCode(): ?int | setCode(?int code): void |
| `details` | [`?(ProtobufAny[])`](../../doc/models/protobuf-any.md) | Optional | - | getDetails(): ?array | setDetails(?array details): void |
| `message` | `?string` | Optional | - | getMessage(): ?string | setMessage(?string message): void |

## Example

```php
try {
    // make the API call
} catch (RpcStatusException $exp) {
    echo 'Caught RpcStatusException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught ApiException:', $exp;
}
```

