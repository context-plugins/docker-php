
# Join Tokens 1

## Structure

`JoinTokens1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `manager` | `?string` | Optional | The token managers can use to join the swarm. | getManager(): ?string | setManager(?string manager): void |
| `worker` | `?string` | Optional | The token workers can use to join the swarm. | getWorker(): ?string | setWorker(?string worker): void |

## Example

```php
use DockerLib\Models\Builders\JoinTokens1Builder;

$joinTokens1 = JoinTokens1Builder::init()
    ->manager('SWMTKN-1-3pu6hszjas19xyp7ghgosyx9k8atbfcr8p2is99znpy26u2lkl-7p73s1dx5in4tatdymyhg9hu2')
    ->worker('SWMTKN-1-3pu6hszjas19xyp7ghgosyx9k8atbfcr8p2is99znpy26u2lkl-1awxwuwd3z9j1z3puu7rcgdbx')
    ->build();
```

