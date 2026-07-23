
# Page

## Structure

`Page`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `count` | `?int` | Optional | total number of results available across all pages | getCount(): ?int | setCount(?int count): void |
| `next` | `?string` | Optional | link to next page of results if any | getNext(): ?string | setNext(?string next): void |
| `previous` | `?string` | Optional | link to previous page of results  if any | getPrevious(): ?string | setPrevious(?string previous): void |

## Example

```php
use DockerLib\Models\Builders\PageBuilder;

$page = PageBuilder::init()
    ->count(226)
    ->next('next6')
    ->previous('previous6')
    ->build();
```

