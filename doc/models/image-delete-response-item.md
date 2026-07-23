
# Image Delete Response Item

## Structure

`ImageDeleteResponseItem`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `deleted` | `?string` | Optional | The image ID of an image that was deleted | getDeleted(): ?string | setDeleted(?string deleted): void |
| `untagged` | `?string` | Optional | The image ID of an image that was untagged | getUntagged(): ?string | setUntagged(?string untagged): void |

## Example

```php
use DockerLib\Models\Builders\ImageDeleteResponseItemBuilder;

$imageDeleteResponseItem = ImageDeleteResponseItemBuilder::init()
    ->deleted('Deleted4')
    ->untagged('Untagged0')
    ->build();
```

