
# Platform

Platform represents the platform (Arch/OS).

## Structure

`Platform`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `architecture` | `?string` | Optional | Architecture represents the hardware architecture (for example,<br>`x86_64`). | getArchitecture(): ?string | setArchitecture(?string architecture): void |
| `oS` | `?string` | Optional | OS represents the Operating System (for example, `linux` or `windows`). | getOS(): ?string | setOS(?string oS): void |

## Example

```php
use DockerLib\Models\Builders\PlatformBuilder;

$platform = PlatformBuilder::init()
    ->architecture('x86_64')
    ->oS('linux')
    ->build();
```

