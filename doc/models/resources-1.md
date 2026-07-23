
# Resources 1

Resource requirements which apply to each individual container created as part of the service.

## Structure

`Resources1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `limits` | [`?Limits`](../../doc/models/limits.md) | Optional | - | getLimits(): ?Limits | setLimits(?Limits limits): void |
| `reservation` | [`?Reservation`](../../doc/models/reservation.md) | Optional | - | getReservation(): ?Reservation | setReservation(?Reservation reservation): void |

## Example

```php
use DockerLib\Models\Builders\Resources1Builder;
use DockerLib\Models\Builders\LimitsBuilder;
use DockerLib\Models\Builders\GenericResourceBuilder;
use DockerLib\Models\Builders\ReservationBuilder;

$resources1 = Resources1Builder::init()
    ->limits(
        LimitsBuilder::init()
            ->genericResources(
                [
                    null,
                    GenericResourceBuilder::init()->build()
                ]
            )
            ->memoryBytes(76)
            ->nanoCPUs(100)
            ->build()
    )
    ->reservation(
        ReservationBuilder::init()
            ->genericResources(
                [
                    GenericResourceBuilder::init()->build(),
                    GenericResourceBuilder::init()->build()
                ]
            )
            ->memoryBytes(134)
            ->nanoCPUs(158)
            ->build()
    )
    ->build();
```

