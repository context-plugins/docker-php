
# Containers Top Response

## Structure

`ContainersTopResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `processes` | `?(string[][])` | Optional | Each process running in the container, where each is process is an array of values corresponding to the titles | getProcesses(): ?array | setProcesses(?array processes): void |
| `titles` | `?(string[])` | Optional | The ps column titles | getTitles(): ?array | setTitles(?array titles): void |

## Example

```php
use DockerLib\Models\Builders\ContainersTopResponseBuilder;

$containersTopResponse = ContainersTopResponseBuilder::init()
    ->processes(
        [
            [
                'Processes7'
            ]
        ]
    )
    ->titles(
        [
            'Titles2',
            'Titles3',
            'Titles4'
        ]
    )
    ->build();
```

