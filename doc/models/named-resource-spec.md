
# Named Resource Spec

## Structure

`NamedResourceSpec`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `kind` | `?string` | Optional | - | getKind(): ?string | setKind(?string kind): void |
| `value` | `?string` | Optional | - | getValue(): ?string | setValue(?string value): void |

## Example

```php
use DockerLib\Models\Builders\NamedResourceSpecBuilder;

$namedResourceSpec = NamedResourceSpecBuilder::init()
    ->kind('Kind6')
    ->value('Value0')
    ->build();
```

