
# Resources

A container's resources (cgroups config, ulimits, etc)

## Structure

`Resources`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `blkioDeviceReadBps` | [`?(ThrottleDevice[])`](../../doc/models/throttle-device.md) | Optional | Limit read rate (bytes per second) from a device, in the form `[{"Path": "device_path", "Rate": rate}]`. | getBlkioDeviceReadBps(): ?array | setBlkioDeviceReadBps(?array blkioDeviceReadBps): void |
| `blkioDeviceReadIOps` | [`?(ThrottleDevice[])`](../../doc/models/throttle-device.md) | Optional | Limit read rate (IO per second) from a device, in the form `[{"Path": "device_path", "Rate": rate}]`. | getBlkioDeviceReadIOps(): ?array | setBlkioDeviceReadIOps(?array blkioDeviceReadIOps): void |
| `blkioDeviceWriteBps` | [`?(ThrottleDevice[])`](../../doc/models/throttle-device.md) | Optional | Limit write rate (bytes per second) to a device, in the form `[{"Path": "device_path", "Rate": rate}]`. | getBlkioDeviceWriteBps(): ?array | setBlkioDeviceWriteBps(?array blkioDeviceWriteBps): void |
| `blkioDeviceWriteIOps` | [`?(ThrottleDevice[])`](../../doc/models/throttle-device.md) | Optional | Limit write rate (IO per second) to a device, in the form `[{"Path": "device_path", "Rate": rate}]`. | getBlkioDeviceWriteIOps(): ?array | setBlkioDeviceWriteIOps(?array blkioDeviceWriteIOps): void |
| `blkioWeight` | `?int` | Optional | Block IO weight (relative weight).<br><br>**Constraints**: `>= 0`, `<= 1000` | getBlkioWeight(): ?int | setBlkioWeight(?int blkioWeight): void |
| `blkioWeightDevice` | [`?(BlkioWeightDevice[])`](../../doc/models/blkio-weight-device.md) | Optional | Block IO weight (relative device weight) in the form `[{"Path": "device_path", "Weight": weight}]`. | getBlkioWeightDevice(): ?array | setBlkioWeightDevice(?array blkioWeightDevice): void |
| `cgroupParent` | `?string` | Optional | Path to `cgroups` under which the container's `cgroup` is created. If the path is not absolute, the path is considered to be relative to the `cgroups` path of the init process. Cgroups are created if they do not already exist. | getCgroupParent(): ?string | setCgroupParent(?string cgroupParent): void |
| `cpuCount` | `?int` | Optional | The number of usable CPUs (Windows only).<br><br>On Windows Server containers, the processor resource controls are mutually exclusive. The order of precedence is `CPUCount` first, then `CPUShares`, and `CPUPercent` last. | getCpuCount(): ?int | setCpuCount(?int cpuCount): void |
| `cpuPercent` | `?int` | Optional | The usable percentage of the available CPUs (Windows only).<br><br>On Windows Server containers, the processor resource controls are mutually exclusive. The order of precedence is `CPUCount` first, then `CPUShares`, and `CPUPercent` last. | getCpuPercent(): ?int | setCpuPercent(?int cpuPercent): void |
| `cpuPeriod` | `?int` | Optional | The length of a CPU period in microseconds. | getCpuPeriod(): ?int | setCpuPeriod(?int cpuPeriod): void |
| `cpuQuota` | `?int` | Optional | Microseconds of CPU time that the container can get in a CPU period. | getCpuQuota(): ?int | setCpuQuota(?int cpuQuota): void |
| `cpuRealtimePeriod` | `?int` | Optional | The length of a CPU real-time period in microseconds. Set to 0 to allocate no time allocated to real-time tasks. | getCpuRealtimePeriod(): ?int | setCpuRealtimePeriod(?int cpuRealtimePeriod): void |
| `cpuRealtimeRuntime` | `?int` | Optional | The length of a CPU real-time runtime in microseconds. Set to 0 to allocate no time allocated to real-time tasks. | getCpuRealtimeRuntime(): ?int | setCpuRealtimeRuntime(?int cpuRealtimeRuntime): void |
| `cpuShares` | `?int` | Optional | An integer value representing this container's relative CPU weight versus other containers. | getCpuShares(): ?int | setCpuShares(?int cpuShares): void |
| `cpusetCpus` | `?string` | Optional | CPUs in which to allow execution (e.g., `0-3`, `0,1`) | getCpusetCpus(): ?string | setCpusetCpus(?string cpusetCpus): void |
| `cpusetMems` | `?string` | Optional | Memory nodes (MEMs) in which to allow execution (0-3, 0,1). Only effective on NUMA systems. | getCpusetMems(): ?string | setCpusetMems(?string cpusetMems): void |
| `deviceCgroupRules` | `?(string[])` | Optional | a list of cgroup rules to apply to the container | getDeviceCgroupRules(): ?array | setDeviceCgroupRules(?array deviceCgroupRules): void |
| `devices` | [`?(DeviceMapping[])`](../../doc/models/device-mapping.md) | Optional | A list of devices to add to the container. | getDevices(): ?array | setDevices(?array devices): void |
| `diskQuota` | `?int` | Optional | Disk limit (in bytes). | getDiskQuota(): ?int | setDiskQuota(?int diskQuota): void |
| `iOMaximumBandwidth` | `?int` | Optional | Maximum IO in bytes per second for the container system drive (Windows only) | getIOMaximumBandwidth(): ?int | setIOMaximumBandwidth(?int iOMaximumBandwidth): void |
| `iOMaximumIOps` | `?int` | Optional | Maximum IOps for the container system drive (Windows only) | getIOMaximumIOps(): ?int | setIOMaximumIOps(?int iOMaximumIOps): void |
| `kernelMemory` | `?int` | Optional | Kernel memory limit in bytes. | getKernelMemory(): ?int | setKernelMemory(?int kernelMemory): void |
| `memory` | `?int` | Optional | Memory limit in bytes.<br><br>**Default**: `0` | getMemory(): ?int | setMemory(?int memory): void |
| `memoryReservation` | `?int` | Optional | Memory soft limit in bytes. | getMemoryReservation(): ?int | setMemoryReservation(?int memoryReservation): void |
| `memorySwap` | `?int` | Optional | Total memory limit (memory + swap). Set as `-1` to enable unlimited swap. | getMemorySwap(): ?int | setMemorySwap(?int memorySwap): void |
| `memorySwappiness` | `?int` | Optional | Tune a container's memory swappiness behavior. Accepts an integer between 0 and 100.<br><br>**Constraints**: `>= 0`, `<= 100` | getMemorySwappiness(): ?int | setMemorySwappiness(?int memorySwappiness): void |
| `nanoCPUs` | `?int` | Optional | CPU quota in units of 10<sup>-9</sup> CPUs. | getNanoCPUs(): ?int | setNanoCPUs(?int nanoCPUs): void |
| `oomKillDisable` | `?bool` | Optional | Disable OOM Killer for the container. | getOomKillDisable(): ?bool | setOomKillDisable(?bool oomKillDisable): void |
| `pidsLimit` | `?int` | Optional | Tune a container's pids limit. Set -1 for unlimited. | getPidsLimit(): ?int | setPidsLimit(?int pidsLimit): void |
| `ulimits` | [`?(Ulimit[])`](../../doc/models/ulimit.md) | Optional | A list of resource limits to set in the container. For example: `{"Name": "nofile", "Soft": 1024, "Hard": 2048}`" | getUlimits(): ?array | setUlimits(?array ulimits): void |

## Example

```php
use DockerLib\Models\Builders\ResourcesBuilder;
use DockerLib\Models\Builders\ThrottleDeviceBuilder;

$resources = ResourcesBuilder::init()
    ->blkioDeviceReadBps(
        [
            ThrottleDeviceBuilder::init()
                ->path('Path0')
                ->rate(72)
                ->build()
        ]
    )
    ->blkioDeviceReadIOps(
        [
            ThrottleDeviceBuilder::init()
                ->path('Path4')
                ->rate(40)
                ->build(),
            ThrottleDeviceBuilder::init()
                ->path('Path4')
                ->rate(40)
                ->build()
        ]
    )
    ->blkioDeviceWriteBps(
        [
            ThrottleDeviceBuilder::init()
                ->path('Path2')
                ->rate(88)
                ->build()
        ]
    )
    ->blkioDeviceWriteIOps(
        [
            ThrottleDeviceBuilder::init()
                ->path('Path2')
                ->rate(206)
                ->build(),
            ThrottleDeviceBuilder::init()
                ->path('Path2')
                ->rate(206)
                ->build(),
            ThrottleDeviceBuilder::init()
                ->path('Path2')
                ->rate(206)
                ->build()
        ]
    )
    ->blkioWeight(100)
    ->cpusetCpus('0-3')
    ->memory(0)
    ->build();
```

