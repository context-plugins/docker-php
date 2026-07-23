
# SE Linux Context 2

## Structure

`SELinuxContext2`

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
use DockerLib\Models\Builders\SELinuxContext2Builder;

$sELinuxContext2 = SELinuxContext2Builder::init()
    ->disable(false)
    ->level('Level4')
    ->role('Role8')
    ->type('Type8')
    ->user('User8')
    ->build();
```

