
# Descriptor 1

## Structure

`Descriptor1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `digest` | `?string` | Optional | - | getDigest(): ?string | setDigest(?string digest): void |
| `mediaType` | `?string` | Optional | - | getMediaType(): ?string | setMediaType(?string mediaType): void |
| `size` | `?int` | Optional | - | getSize(): ?int | setSize(?int size): void |
| `uRLs` | `?(string[])` | Optional | - | getURLs(): ?array | setURLs(?array uRLs): void |

## Example

```php
use DockerLib\Models\Builders\Descriptor1Builder;

$descriptor1 = Descriptor1Builder::init()
    ->digest('Digest4')
    ->mediaType('MediaType2')
    ->size(248)
    ->uRLs(
        [
            'URLs7',
            'URLs8'
        ]
    )
    ->build();
```

