
# Descriptor

A descriptor struct containing digest, media type, and size

## Structure

`Descriptor`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `digest` | `?string` | Optional | - | getDigest(): ?string | setDigest(?string digest): void |
| `mediaType` | `?string` | Optional | - | getMediaType(): ?string | setMediaType(?string mediaType): void |
| `size` | `?int` | Optional | - | getSize(): ?int | setSize(?int size): void |
| `uRLs` | `?(string[])` | Optional | - | getURLs(): ?array | setURLs(?array uRLs): void |

## Example

```php
use DockerLib\Models\Builders\DescriptorBuilder;

$descriptor = DescriptorBuilder::init()
    ->digest('Digest2')
    ->mediaType('MediaType8')
    ->size(146)
    ->uRLs(
        [
            'URLs3'
        ]
    )
    ->build();
```

