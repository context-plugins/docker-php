
# Raft

Raft configuration.

## Structure

`Raft`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `electionTick` | `?int` | Optional | The number of ticks that a follower will wait for a message from the leader before becoming a candidate and starting an election. `ElectionTick` must be greater than `HeartbeatTick`.<br><br>A tick currently defaults to one second, so these translate directly to seconds currently, but this is NOT guaranteed. | getElectionTick(): ?int | setElectionTick(?int electionTick): void |
| `heartbeatTick` | `?int` | Optional | The number of ticks between heartbeats. Every HeartbeatTick ticks, the leader will send a heartbeat to the followers.<br><br>A tick currently defaults to one second, so these translate directly to seconds currently, but this is NOT guaranteed. | getHeartbeatTick(): ?int | setHeartbeatTick(?int heartbeatTick): void |
| `keepOldSnapshots` | `?int` | Optional | The number of snapshots to keep beyond the current snapshot. | getKeepOldSnapshots(): ?int | setKeepOldSnapshots(?int keepOldSnapshots): void |
| `logEntriesForSlowFollowers` | `?int` | Optional | The number of log entries to keep around to sync up slow followers after a snapshot is created. | getLogEntriesForSlowFollowers(): ?int | setLogEntriesForSlowFollowers(?int logEntriesForSlowFollowers): void |
| `snapshotInterval` | `?int` | Optional | The number of log entries between snapshots. | getSnapshotInterval(): ?int | setSnapshotInterval(?int snapshotInterval): void |

## Example

```php
use DockerLib\Models\Builders\RaftBuilder;

$raft = RaftBuilder::init()
    ->electionTick(3)
    ->heartbeatTick(1)
    ->keepOldSnapshots(32)
    ->logEntriesForSlowFollowers(500)
    ->snapshotInterval(10000)
    ->build();
```

