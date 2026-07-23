
# SE Linux Context

SELinux labels of the container

## Structure

`SELinuxContext`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `disable` | `?bool` | Optional | Disable SELinux | getDisable(): ?bool | setDisable(?bool disable): void |
| `level` | `?string` | Optional | SELinux level label | getLevel(): ?string | setLevel(?string level): void |
| `role` | `?string` | Optional | SELinux role label | getRole(): ?string | setRole(?string role): void |
| `type` | `?string` | Optional | SELinux type label | getType(): ?string | setType(?string type): void |
| `user` | `?string` | Optional | SELinux user label | getUser(): ?string | setUser(?string user): void |

## Example

```php
use DockerLib\Models\Builders\SELinuxContextBuilder;

$sELinuxContext = SELinuxContextBuilder::init()
    ->disable(false)
    ->level('Level8')
    ->role('Role0')
    ->type('Type6')
    ->user('User0')
    ->build();
```

