
# Get Access Tokens Response

## Structure

`GetAccessTokensResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `activeCount` | `?float` | Optional | - | getActiveCount(): ?float | setActiveCount(?float activeCount): void |
| `count` | `?float` | Optional | - | getCount(): ?float | setCount(?float count): void |
| `next` | `?string` | Optional | - | getNext(): ?string | setNext(?string next): void |
| `previous` | `?string` | Optional | - | getPrevious(): ?string | setPrevious(?string previous): void |
| `results` | [`?(AccessToken[])`](../../doc/models/access-token.md) | Optional | - | getResults(): ?array | setResults(?array results): void |

## Example

```php
use DockerLib\Models\Builders\GetAccessTokensResponseBuilder;
use DockerLib\Models\Builders\AccessTokenBuilder;

$getAccessTokensResponse = GetAccessTokensResponseBuilder::init()
    ->activeCount(1)
    ->count(1)
    ->next('next6')
    ->previous('previous6')
    ->results(
        [
            AccessTokenBuilder::init()
                ->clientId('client_id8')
                ->createdAt('created_at4')
                ->creatorIp('creator_ip2')
                ->creatorUa('creator_ua6')
                ->generatedBy('generated_by6')
                ->build(),
            AccessTokenBuilder::init()
                ->clientId('client_id8')
                ->createdAt('created_at4')
                ->creatorIp('creator_ip2')
                ->creatorUa('creator_ua6')
                ->generatedBy('generated_by6')
                ->build(),
            AccessTokenBuilder::init()
                ->clientId('client_id8')
                ->createdAt('created_at4')
                ->creatorIp('creator_ip2')
                ->creatorUa('creator_ua6')
                ->generatedBy('generated_by6')
                ->build()
        ]
    )
    ->build();
```

