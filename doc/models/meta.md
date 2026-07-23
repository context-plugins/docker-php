
# Meta

## Structure

`Meta`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `created` | `?string` | Optional | The creation date for the user as a RFC3339 formatted string. | getCreated(): ?string | setCreated(?string created): void |
| `lastModified` | `?string` | Optional | The date the user was last modified as a RFC3339 formatted string. | getLastModified(): ?string | setLastModified(?string lastModified): void |
| `location` | `?string` | Optional | - | getLocation(): ?string | setLocation(?string location): void |
| `resourceType` | `?string` | Optional | - | getResourceType(): ?string | setResourceType(?string resourceType): void |

## Example

```php
use DockerLib\Models\Builders\MetaBuilder;

$meta = MetaBuilder::init()
    ->created('2022-05-20T00:54:18Z')
    ->lastModified('2022-05-20T00:54:18Z')
    ->location('https://hub.docker.com/v2/scim/2.0/Users/d80f7c79-7730-49d8-9a41-7c42fb622d9c')
    ->resourceType('User')
    ->build();
```

