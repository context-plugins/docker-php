
# Swarm Unlockkey Response

## Structure

`SwarmUnlockkeyResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `unlockKey` | `?string` | Optional | The swarm's unlock key. | getUnlockKey(): ?string | setUnlockKey(?string unlockKey): void |

## Example

```php
use DockerLib\Models\Builders\SwarmUnlockkeyResponseBuilder;

$swarmUnlockkeyResponse = SwarmUnlockkeyResponseBuilder::init()
    ->unlockKey('SWMKEY-1-7c37Cc8654o6p38HnroywCi19pllOnGtbdZEgtKxZu8')
    ->build();
```

