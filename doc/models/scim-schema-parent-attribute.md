
# Scim Schema Parent Attribute

## Structure

`ScimSchemaParentAttribute`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `caseExact` | `?bool` | Optional | - | getCaseExact(): ?bool | setCaseExact(?bool caseExact): void |
| `description` | `?string` | Optional | - | getDescription(): ?string | setDescription(?string description): void |
| `multiValued` | `?bool` | Optional | - | getMultiValued(): ?bool | setMultiValued(?bool multiValued): void |
| `mutability` | `?string` | Optional | - | getMutability(): ?string | setMutability(?string mutability): void |
| `name` | `?string` | Optional | - | getName(): ?string | setName(?string name): void |
| `required` | `?bool` | Optional | - | getRequired(): ?bool | setRequired(?bool required): void |
| `returned` | `?string` | Optional | - | getReturned(): ?string | setReturned(?string returned): void |
| `type` | [`?string(Type3Enum)`](../../doc/models/type-3-enum.md) | Optional | - | getType(): ?string | setType(?string type): void |
| `uniqueness` | `?string` | Optional | - | getUniqueness(): ?string | setUniqueness(?string uniqueness): void |
| `subAttributes` | [`?(ScimSchemaAttribute[])`](../../doc/models/scim-schema-attribute.md) | Optional | - | getSubAttributes(): ?array | setSubAttributes(?array subAttributes): void |

## Example

```php
use DockerLib\Models\Builders\ScimSchemaParentAttributeBuilder;

$scimSchemaParentAttribute = ScimSchemaParentAttributeBuilder::init()
    ->caseExact(false)
    ->description('Unique identifier for the User, typically used by the user to directly authenticate to the service provider. Each User MUST include a non-empty userName value. This identifier MUST be unique across the service provider\'s entire set of Users.')
    ->multiValued(false)
    ->mutability('readWrite')
    ->name('userName')
    ->required(true)
    ->returned('default')
    ->uniqueness('server')
    ->build();
```

