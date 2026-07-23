
# Runc Commit

## Structure

`RuncCommit`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `expected` | `?string` | Optional | Commit ID of external tool expected by dockerd as set at build time. | getExpected(): ?string | setExpected(?string expected): void |
| `iD` | `?string` | Optional | Actual commit ID of external tool. | getID(): ?string | setID(?string iD): void |

## Example

```php
use DockerLib\Models\Builders\RuncCommitBuilder;

$runcCommit = RuncCommitBuilder::init()
    ->expected('2d41c047c83e09a6d61d464906feb2a2f3c52aa4')
    ->iD('cfb82a876ecc11b5ca0977d1733adbe58599088a')
    ->build();
```

