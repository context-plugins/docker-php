
# Host Config

Container configuration that depends on the host we are running on

## Structure

`HostConfig`

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
| `autoRemove` | `?bool` | Optional | Automatically remove the container when the container's process exits. This has no effect if `RestartPolicy` is set. | getAutoRemove(): ?bool | setAutoRemove(?bool autoRemove): void |
| `binds` | `?(string[])` | Optional | A list of volume bindings for this container. Each volume binding is a string in one of these forms:<br><br>- `host-src:container-dest` to bind-mount a host path into the container. Both `host-src`, and `container-dest` must be an _absolute_ path.<br>- `host-src:container-dest:ro` to make the bind mount read-only inside the container. Both `host-src`, and `container-dest` must be an _absolute_ path.<br>- `volume-name:container-dest` to bind-mount a volume managed by a volume driver into the container. `container-dest` must be an _absolute_ path.<br>- `volume-name:container-dest:ro` to mount the volume read-only inside the container.  `container-dest` must be an _absolute_ path. | getBinds(): ?array | setBinds(?array binds): void |
| `capAdd` | `?(string[])` | Optional | A list of kernel capabilities to add to the container. | getCapAdd(): ?array | setCapAdd(?array capAdd): void |
| `capDrop` | `?(string[])` | Optional | A list of kernel capabilities to drop from the container. | getCapDrop(): ?array | setCapDrop(?array capDrop): void |
| `cgroup` | `?string` | Optional | Cgroup to use for the container. | getCgroup(): ?string | setCgroup(?string cgroup): void |
| `consoleSize` | `?(int[])` | Optional | Initial console size, as an `[height, width]` array. (Windows only)<br><br>**Constraints**: *Minimum Items*: `2`, *Maximum Items*: `2`, `>= 0` | getConsoleSize(): ?array | setConsoleSize(?array consoleSize): void |
| `containerIDFile` | `?string` | Optional | Path to a file where the container ID is written | getContainerIDFile(): ?string | setContainerIDFile(?string containerIDFile): void |
| `dns` | `?(string[])` | Optional | A list of DNS servers for the container to use. | getDns(): ?array | setDns(?array dns): void |
| `dnsOptions` | `?(string[])` | Optional | A list of DNS options. | getDnsOptions(): ?array | setDnsOptions(?array dnsOptions): void |
| `dnsSearch` | `?(string[])` | Optional | A list of DNS search domains. | getDnsSearch(): ?array | setDnsSearch(?array dnsSearch): void |
| `extraHosts` | `?(string[])` | Optional | A list of hostnames/IP mappings to add to the container's `/etc/hosts` file. Specified in the form `["hostname:IP"]`. | getExtraHosts(): ?array | setExtraHosts(?array extraHosts): void |
| `groupAdd` | `?(string[])` | Optional | A list of additional groups that the container process will run as. | getGroupAdd(): ?array | setGroupAdd(?array groupAdd): void |
| `ipcMode` | `?string` | Optional | IPC sharing mode for the container. Possible values are:<br><br>- `"none"`: own private IPC namespace, with /dev/shm not mounted<br>- `"private"`: own private IPC namespace<br>- `"shareable"`: own private IPC namespace, with a possibility to share it with other containers<br>- `"container:<name\|id>"`: join another (shareable) container's IPC namespace<br>- `"host"`: use the host system's IPC namespace<br><br>If not specified, daemon default is used, which can either be `"private"`<br>or `"shareable"`, depending on daemon version and configuration. | getIpcMode(): ?string | setIpcMode(?string ipcMode): void |
| `isolation` | [`?string(IsolationEnum)`](../../doc/models/isolation-enum.md) | Optional | - | getIsolation(): ?string | setIsolation(?string isolation): void |
| `links` | `?(string[])` | Optional | A list of links for the container in the form `container_name:alias`. | getLinks(): ?array | setLinks(?array links): void |
| `logConfig` | [`?LogConfig2`](../../doc/models/log-config-2.md) | Optional | - | getLogConfig(): ?LogConfig2 | setLogConfig(?LogConfig2 logConfig): void |
| `mounts` | [`?(Mount[])`](../../doc/models/mount.md) | Optional | Specification for mounts to be added to the container. | getMounts(): ?array | setMounts(?array mounts): void |
| `networkMode` | `?string` | Optional | Network mode to use for this container. Supported standard values are: `bridge`, `host`, `none`, and `container:<name\|id>`. Any other value is taken as a custom network's name to which this container should connect to. | getNetworkMode(): ?string | setNetworkMode(?string networkMode): void |
| `oomScoreAdj` | `?int` | Optional | An integer value containing the score given to the container in order to tune OOM killer preferences. | getOomScoreAdj(): ?int | setOomScoreAdj(?int oomScoreAdj): void |
| `pidMode` | `?string` | Optional | Set the PID (Process) Namespace mode for the container. It can be either:<br><br>- `"container:<name\|id>"`: joins another container's PID namespace<br>- `"host"`: use the host's PID namespace inside the container | getPidMode(): ?string | setPidMode(?string pidMode): void |
| `portBindings` | [`?array<string,PortBindings>`](../../doc/models/port-bindings.md) | Optional | A map of exposed container ports and the host port they should map to. | getPortBindings(): ?array | setPortBindings(?array portBindings): void |
| `privileged` | `?bool` | Optional | Gives the container full access to the host. | getPrivileged(): ?bool | setPrivileged(?bool privileged): void |
| `publishAllPorts` | `?bool` | Optional | Allocates a random host port for all of a container's exposed ports. | getPublishAllPorts(): ?bool | setPublishAllPorts(?bool publishAllPorts): void |
| `readonlyRootfs` | `?bool` | Optional | Mount the container's root filesystem as read only. | getReadonlyRootfs(): ?bool | setReadonlyRootfs(?bool readonlyRootfs): void |
| `restartPolicy` | [`?RestartPolicy3`](../../doc/models/restart-policy-3.md) | Optional | - | getRestartPolicy(): ?RestartPolicy3 | setRestartPolicy(?RestartPolicy3 restartPolicy): void |
| `runtime` | `?string` | Optional | Runtime to use with this container. | getRuntime(): ?string | setRuntime(?string runtime): void |
| `securityOpt` | `?(string[])` | Optional | A list of string values to customize labels for MLS systems, such as SELinux. | getSecurityOpt(): ?array | setSecurityOpt(?array securityOpt): void |
| `shmSize` | `?int` | Optional | Size of `/dev/shm` in bytes. If omitted, the system uses 64MB.<br><br>**Constraints**: `>= 0` | getShmSize(): ?int | setShmSize(?int shmSize): void |
| `storageOpt` | `?array<string,string>` | Optional | Storage driver options for this container, in the form `{"size": "120G"}`. | getStorageOpt(): ?array | setStorageOpt(?array storageOpt): void |
| `sysctls` | `?array<string,string>` | Optional | A list of kernel parameters (sysctls) to set in the container. For example: `{"net.ipv4.ip_forward": "1"}` | getSysctls(): ?array | setSysctls(?array sysctls): void |
| `tmpfs` | `?array<string,string>` | Optional | A map of container directories which should be replaced by tmpfs mounts, and their corresponding mount options. For example: `{ "/run": "rw,noexec,nosuid,size=65536k" }`. | getTmpfs(): ?array | setTmpfs(?array tmpfs): void |
| `uTSMode` | `?string` | Optional | UTS namespace to use for the container. | getUTSMode(): ?string | setUTSMode(?string uTSMode): void |
| `usernsMode` | `?string` | Optional | Sets the usernamespace mode for the container when usernamespace remapping option is enabled. | getUsernsMode(): ?string | setUsernsMode(?string usernsMode): void |
| `volumeDriver` | `?string` | Optional | Driver that this container uses to mount volumes. | getVolumeDriver(): ?string | setVolumeDriver(?string volumeDriver): void |
| `volumesFrom` | `?(string[])` | Optional | A list of volumes to inherit from another container, specified in the form `<container name>[:<ro\|rw>]`. | getVolumesFrom(): ?array | setVolumesFrom(?array volumesFrom): void |

## Example

```php
use DockerLib\Models\Builders\HostConfigBuilder;
use DockerLib\Models\Builders\ThrottleDeviceBuilder;

$hostConfig = HostConfigBuilder::init()
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
    ->blkioWeight(102)
    ->cpusetCpus('0-3')
    ->memory(0)
    ->oomScoreAdj(500)
    ->build();
```

