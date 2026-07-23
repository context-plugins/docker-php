
# Usage Data

Usage details about the volume. This information is used by the
`GET /system/df` endpoint, and omitted in other endpoints.

## Structure

`UsageData`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `refCount` | `int` | Required | The number of containers referencing this volume. This field<br>is set to `-1` if the reference-count is not available. | getRefCount(): int | setRefCount(int refCount): void |
| `size` | `int` | Required | Amount of disk space used by the volume (in bytes). This information<br>is only available for volumes created with the `"local"` volume<br>driver. For volumes created with other volume drivers, this field<br>is set to `-1` ("not available") | getSize(): int | setSize(int size): void |

## Example

```php
use DockerLib\Models\Builders\UsageDataBuilder;

$usageData = UsageDataBuilder::init(
    14,
    176
)->build();
```

