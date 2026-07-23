
# System Info

## Structure

`SystemInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `architecture` | `?string` | Optional | Hardware architecture of the host, as returned by the Go runtime<br>(`GOARCH`).<br><br>A full list of possible values can be found in the [Go documentation](https://golang.org/doc/install/source#environment). | getArchitecture(): ?string | setArchitecture(?string architecture): void |
| `bridgeNfIp6tables` | `?bool` | Optional | Indicates if `bridge-nf-call-ip6tables` is available on the host. | getBridgeNfIp6tables(): ?bool | setBridgeNfIp6tables(?bool bridgeNfIp6tables): void |
| `bridgeNfIptables` | `?bool` | Optional | Indicates if `bridge-nf-call-iptables` is available on the host. | getBridgeNfIptables(): ?bool | setBridgeNfIptables(?bool bridgeNfIptables): void |
| `cPUSet` | `?bool` | Optional | Indicates if CPUsets (cpuset.cpus, cpuset.mems) are supported by the host.<br><br>See [cpuset(7)](https://www.kernel.org/doc/Documentation/cgroup-v1/cpusets.txt) | getCPUSet(): ?bool | setCPUSet(?bool cPUSet): void |
| `cPUShares` | `?bool` | Optional | Indicates if CPU Shares limiting is supported by the host. | getCPUShares(): ?bool | setCPUShares(?bool cPUShares): void |
| `cgroupDriver` | [`?string(CgroupDriverEnum)`](../../doc/models/cgroup-driver-enum.md) | Optional | - | getCgroupDriver(): ?string | setCgroupDriver(?string cgroupDriver): void |
| `clusterAdvertise` | `?string` | Optional | The network endpoint that the Engine advertises for the purpose of<br>node discovery. ClusterAdvertise is a `host:port` combination on which<br>the daemon is reachable by other hosts.<br><br><p><br /></p><br>> **Note**: This field is only propagated when using standalone Swarm<br>> mode, and overlay networking using an external k/v store. Overlay<br>> networks with Swarm mode enabled use the built-in raft store, and<br>> this field will be empty.<br> | getClusterAdvertise(): ?string | setClusterAdvertise(?string clusterAdvertise): void |
| `clusterStore` | `?string` | Optional | URL of the distributed storage backend.<br><br>The storage backend is used for multihost networking (to store<br>network and endpoint information) and by the node discovery mechanism.<br><br><p><br /></p><br>> **Note**: This field is only propagated when using standalone Swarm<br>> mode, and overlay networking using an external k/v store. Overlay<br>> networks with Swarm mode enabled use the built-in raft store, and<br>> this field will be empty.<br> | getClusterStore(): ?string | setClusterStore(?string clusterStore): void |
| `containerdCommit` | [`?ContainerdCommit`](../../doc/models/containerd-commit.md) | Optional | - | getContainerdCommit(): ?ContainerdCommit | setContainerdCommit(?ContainerdCommit containerdCommit): void |
| `containers` | `?int` | Optional | Total number of containers on the host. | getContainers(): ?int | setContainers(?int containers): void |
| `containersPaused` | `?int` | Optional | Number of containers with status `"paused"`. | getContainersPaused(): ?int | setContainersPaused(?int containersPaused): void |
| `containersRunning` | `?int` | Optional | Number of containers with status `"running"`. | getContainersRunning(): ?int | setContainersRunning(?int containersRunning): void |
| `containersStopped` | `?int` | Optional | Number of containers with status `"stopped"`. | getContainersStopped(): ?int | setContainersStopped(?int containersStopped): void |
| `cpuCfsPeriod` | `?bool` | Optional | Indicates if CPU CFS(Completely Fair Scheduler) period is supported by the host. | getCpuCfsPeriod(): ?bool | setCpuCfsPeriod(?bool cpuCfsPeriod): void |
| `cpuCfsQuota` | `?bool` | Optional | Indicates if CPU CFS(Completely Fair Scheduler) quota is supported by the host. | getCpuCfsQuota(): ?bool | setCpuCfsQuota(?bool cpuCfsQuota): void |
| `debug` | `?bool` | Optional | Indicates if the daemon is running in debug-mode / with debug-level logging enabled. | getDebug(): ?bool | setDebug(?bool debug): void |
| `defaultRuntime` | `?string` | Optional | Name of the default OCI runtime that is used when starting containers.<br><br>The default can be overridden per-container at create time.<br><br>**Default**: `'runc'` | getDefaultRuntime(): ?string | setDefaultRuntime(?string defaultRuntime): void |
| `dockerRootDir` | `?string` | Optional | Root directory of persistent Docker state.<br><br>Defaults to `/var/lib/docker` on Linux, and `C:\ProgramData\docker`<br>on Windows. | getDockerRootDir(): ?string | setDockerRootDir(?string dockerRootDir): void |
| `driver` | `?string` | Optional | Name of the storage driver in use. | getDriver(): ?string | setDriver(?string driver): void |
| `driverStatus` | `?(string[][])` | Optional | Information specific to the storage driver, provided as<br>"label" / "value" pairs.<br><br>This information is provided by the storage driver, and formatted<br>in a way consistent with the output of `docker info` on the command<br>line.<br><br><p><br /></p><br>> **Note**: The information returned in this field, including the<br>> formatting of values and labels, should not be considered stable,<br>> and may change without notice.<br> | getDriverStatus(): ?array | setDriverStatus(?array driverStatus): void |
| `experimentalBuild` | `?bool` | Optional | Indicates if experimental features are enabled on the daemon. | getExperimentalBuild(): ?bool | setExperimentalBuild(?bool experimentalBuild): void |
| `genericResources` | [`?(GenericResource[])`](../../doc/models/generic-resource.md) | Optional | User-defined resources can be either Integer resources (e.g, `SSD=3`) or String resources (e.g, `GPU=UUID1`) | getGenericResources(): ?array | setGenericResources(?array genericResources): void |
| `httpProxy` | `?string` | Optional | HTTP-proxy configured for the daemon. This value is obtained from the<br>[`HTTP_PROXY`](https://www.gnu.org/software/wget/manual/html_node/Proxies.html) environment variable.<br><br>Containers do not automatically inherit this configuration. | getHttpProxy(): ?string | setHttpProxy(?string httpProxy): void |
| `httpsProxy` | `?string` | Optional | HTTPS-proxy configured for the daemon. This value is obtained from the<br>[`HTTPS_PROXY`](https://www.gnu.org/software/wget/manual/html_node/Proxies.html) environment variable.<br><br>Containers do not automatically inherit this configuration. | getHttpsProxy(): ?string | setHttpsProxy(?string httpsProxy): void |
| `iD` | `?string` | Optional | Unique identifier of the daemon.<br><br><p><br /></p><br>> **Note**: The format of the ID itself is not part of the API, and<br>> should not be considered stable.<br> | getID(): ?string | setID(?string iD): void |
| `iPv4Forwarding` | `?bool` | Optional | Indicates IPv4 forwarding is enabled. | getIPv4Forwarding(): ?bool | setIPv4Forwarding(?bool iPv4Forwarding): void |
| `images` | `?int` | Optional | Total number of images on the host.<br><br>Both _tagged_ and _untagged_ (dangling) images are counted. | getImages(): ?int | setImages(?int images): void |
| `indexServerAddress` | `?string` | Optional | Address / URL of the index server that is used for image search,<br>and as a default for user authentication for Docker Hub and Docker Cloud.<br><br>**Default**: `'https://index.docker.io/v1/'` | getIndexServerAddress(): ?string | setIndexServerAddress(?string indexServerAddress): void |
| `initBinary` | `?string` | Optional | Name and, optional, path of the the `docker-init` binary.<br><br>If the path is omitted, the daemon searches the host's `$PATH` for the<br>binary and uses the first result. | getInitBinary(): ?string | setInitBinary(?string initBinary): void |
| `initCommit` | [`?InitCommit`](../../doc/models/init-commit.md) | Optional | - | getInitCommit(): ?InitCommit | setInitCommit(?InitCommit initCommit): void |
| `isolation` | [`?string(Isolation1Enum)`](../../doc/models/isolation-1-enum.md) | Optional | - | getIsolation(): ?string | setIsolation(?string isolation): void |
| `kernelMemory` | `?bool` | Optional | Indicates if the host has kernel memory limit support enabled. | getKernelMemory(): ?bool | setKernelMemory(?bool kernelMemory): void |
| `kernelVersion` | `?string` | Optional | Kernel version of the host.<br><br>On Linux, this information obtained from `uname`. On Windows this<br>information is queried from the <kbd>HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\</kbd><br>registry value, for example _"10.0 14393 (14393.1198.amd64fre.rs1_release_sec.170427-1353)"_. | getKernelVersion(): ?string | setKernelVersion(?string kernelVersion): void |
| `labels` | `?(string[])` | Optional | User-defined labels (key/value metadata) as set on the daemon.<br><br><p><br /></p><br>> **Note**: When part of a Swarm, nodes can both have _daemon_ labels,<br>> set through the daemon configuration, and _node_ labels, set from a<br>> manager node in the Swarm. Node labels are not included in this<br>> field. Node labels can be retrieved using the `/nodes/(id)` endpoint<br>> on a manager node in the Swarm.<br> | getLabels(): ?array | setLabels(?array labels): void |
| `liveRestoreEnabled` | `?bool` | Optional | Indicates if live restore is enabled.<br><br>If enabled, containers are kept running when the daemon is shutdown<br>or upon daemon start if running containers are detected.<br><br>**Default**: `false` | getLiveRestoreEnabled(): ?bool | setLiveRestoreEnabled(?bool liveRestoreEnabled): void |
| `loggingDriver` | `?string` | Optional | The logging driver to use as a default for new containers. | getLoggingDriver(): ?string | setLoggingDriver(?string loggingDriver): void |
| `memTotal` | `?int` | Optional | Total amount of physical memory available on the host, in kilobytes (kB). | getMemTotal(): ?int | setMemTotal(?int memTotal): void |
| `memoryLimit` | `?bool` | Optional | Indicates if the host has memory limit support enabled. | getMemoryLimit(): ?bool | setMemoryLimit(?bool memoryLimit): void |
| `nCPU` | `?int` | Optional | The number of logical CPUs usable by the daemon.<br><br>The number of available CPUs is checked by querying the operating<br>system when the daemon starts. Changes to operating system CPU<br>allocation after the daemon is started are not reflected. | getNCPU(): ?int | setNCPU(?int nCPU): void |
| `nEventsListener` | `?int` | Optional | Number of event listeners subscribed. | getNEventsListener(): ?int | setNEventsListener(?int nEventsListener): void |
| `nFd` | `?int` | Optional | The total number of file Descriptors in use by the daemon process.<br><br>This information is only returned if debug-mode is enabled. | getNFd(): ?int | setNFd(?int nFd): void |
| `nGoroutines` | `?int` | Optional | The  number of goroutines that currently exist.<br><br>This information is only returned if debug-mode is enabled. | getNGoroutines(): ?int | setNGoroutines(?int nGoroutines): void |
| `name` | `?string` | Optional | Hostname of the host. | getName(): ?string | setName(?string name): void |
| `noProxy` | `?string` | Optional | Comma-separated list of domain extensions for which no proxy should be<br>used. This value is obtained from the [`NO_PROXY`](https://www.gnu.org/software/wget/manual/html_node/Proxies.html)<br>environment variable.<br><br>Containers do not automatically inherit this configuration. | getNoProxy(): ?string | setNoProxy(?string noProxy): void |
| `oSType` | `?string` | Optional | Generic type of the operating system of the host, as returned by the<br>Go runtime (`GOOS`).<br><br>Currently returned values are "linux" and "windows". A full list of<br>possible values can be found in the [Go documentation](https://golang.org/doc/install/source#environment). | getOSType(): ?string | setOSType(?string oSType): void |
| `oomKillDisable` | `?bool` | Optional | Indicates if OOM killer disable is supported on the host. | getOomKillDisable(): ?bool | setOomKillDisable(?bool oomKillDisable): void |
| `operatingSystem` | `?string` | Optional | Name of the host's operating system, for example: "Ubuntu 16.04.2 LTS"<br>or "Windows Server 2016 Datacenter" | getOperatingSystem(): ?string | setOperatingSystem(?string operatingSystem): void |
| `plugins` | [`?Plugins`](../../doc/models/plugins.md) | Optional | - | getPlugins(): ?Plugins | setPlugins(?Plugins plugins): void |
| `registryConfig` | `?array` | Optional | - | getRegistryConfig(): ?array | setRegistryConfig(?array registryConfig): void |
| `runcCommit` | [`?RuncCommit`](../../doc/models/runc-commit.md) | Optional | - | getRuncCommit(): ?RuncCommit | setRuncCommit(?RuncCommit runcCommit): void |
| `runtimes` | [`?array<string,Runtime>`](../../doc/models/runtime.md) | Optional | List of [OCI compliant](https://github.com/opencontainers/runtime-spec)<br>runtimes configured on the daemon. Keys hold the "name" used to<br>reference the runtime.<br><br>The Docker daemon relies on an OCI compliant runtime (invoked via the<br>`containerd` daemon) as its interface to the Linux kernel namespaces,<br>cgroups, and SELinux.<br><br>The default runtime is `runc`, and automatically configured. Additional<br>runtimes can be configured by the user and will be listed here. | getRuntimes(): ?array | setRuntimes(?array runtimes): void |
| `securityOptions` | `?(string[])` | Optional | List of security features that are enabled on the daemon, such as<br>apparmor, seccomp, SELinux, and user-namespaces (userns).<br><br>Additional configuration options for each security feature may<br>be present, and are included as a comma-separated list of key/value<br>pairs. | getSecurityOptions(): ?array | setSecurityOptions(?array securityOptions): void |
| `serverVersion` | `?string` | Optional | Version string of the daemon.<br><br>> **Note**: the [standalone Swarm API](https://docs.docker.com/swarm/swarm-api/)<br>> returns the Swarm version instead of the daemon  version, for example<br>> `swarm/1.2.8`. | getServerVersion(): ?string | setServerVersion(?string serverVersion): void |
| `swapLimit` | `?bool` | Optional | Indicates if the host has memory swap limit support enabled. | getSwapLimit(): ?bool | setSwapLimit(?bool swapLimit): void |
| `swarm` | [`?Swarm1`](../../doc/models/swarm-1.md) | Optional | - | getSwarm(): ?Swarm1 | setSwarm(?Swarm1 swarm): void |
| `systemStatus` | `?(string[][])` | Optional | Status information about this node (standalone Swarm API).<br><br><p><br /></p><br>> **Note**: The information returned in this field is only propagated<br>> by the Swarm standalone API, and is empty (`null`) when using<br>> built-in swarm mode.<br> | getSystemStatus(): ?array | setSystemStatus(?array systemStatus): void |
| `systemTime` | `?string` | Optional | Current system-time in [RFC 3339](https://www.ietf.org/rfc/rfc3339.txt)<br>format with nano-seconds. | getSystemTime(): ?string | setSystemTime(?string systemTime): void |

## Example

```php
use DockerLib\Models\Builders\SystemInfoBuilder;
use DockerLib\Models\Builders\GenericResourceBuilder;
use DockerLib\Models\Builders\DiscreteResourceSpecBuilder;
use DockerLib\Models\Builders\NamedResourceSpecBuilder;
use DockerLib\Models\Builders\RuntimeBuilder;

$systemInfo = SystemInfoBuilder::init()
    ->architecture('x86_64')
    ->bridgeNfIp6tables(true)
    ->bridgeNfIptables(true)
    ->cPUSet(true)
    ->cPUShares(true)
    ->clusterAdvertise('node5.corp.example.com:8000')
    ->clusterStore('consul://consul.corp.example.com:8600/some/path')
    ->containers(14)
    ->containersPaused(1)
    ->containersRunning(3)
    ->containersStopped(10)
    ->cpuCfsPeriod(true)
    ->cpuCfsQuota(true)
    ->debug(true)
    ->defaultRuntime('runc')
    ->dockerRootDir('/var/lib/docker')
    ->driver('overlay2')
    ->driverStatus(
        [
            [
                'Backing Filesystem',
                'extfs'
            ],
            [
                'Supports d_type',
                'true'
            ],
            [
                'Native Overlay Diff',
                'true'
            ]
        ]
    )
    ->experimentalBuild(true)
    ->genericResources(
        [
            GenericResourceBuilder::init()
                ->discreteResourceSpec(
                    DiscreteResourceSpecBuilder::init()
                        ->kind('SSD')
                        ->value(3)
                        ->build()
                )
                ->build(),
            GenericResourceBuilder::init()
                ->namedResourceSpec(
                    NamedResourceSpecBuilder::init()
                        ->kind('GPU')
                        ->value('UUID1')
                        ->build()
                )
                ->build(),
            GenericResourceBuilder::init()
                ->namedResourceSpec(
                    NamedResourceSpecBuilder::init()
                        ->kind('GPU')
                        ->value('UUID2')
                        ->build()
                )
                ->build()
        ]
    )
    ->httpProxy('http://user:pass@proxy.corp.example.com:8080')
    ->httpsProxy('https://user:pass@proxy.corp.example.com:4443')
    ->iD('7TRN:IPZB:QYBB:VPBQ:UMPP:KARE:6ZNR:XE6T:7EWV:PKF4:ZOJD:TPYS')
    ->iPv4Forwarding(true)
    ->images(508)
    ->indexServerAddress('https://index.docker.io/v1/')
    ->initBinary('docker-init')
    ->kernelMemory(true)
    ->kernelVersion('4.9.38-moby')
    ->labels(
        [
            'storage=ssd',
            'production'
        ]
    )
    ->liveRestoreEnabled(false)
    ->memTotal(2095882240)
    ->memoryLimit(true)
    ->nCPU(4)
    ->nEventsListener(30)
    ->nFd(64)
    ->nGoroutines(174)
    ->name('node5.corp.example.com')
    ->noProxy('*.local, 169.254/16')
    ->oSType('linux')
    ->operatingSystem('Alpine Linux v3.5')
    ->runtimes(
        [
            'custom' => RuntimeBuilder::init()
                ->path('/usr/local/bin/my-oci-runtime')
                ->runtimeArgs(
                    [
                        '--debug',
                        '--systemd-cgroup=false'
                    ]
                )
                ->build(),
            'runc' => RuntimeBuilder::init()
                ->path('docker-runc')
                ->build(),
            'runc-master' => RuntimeBuilder::init()
                ->path('/go/bin/runc')
                ->build()
        ]
    )
    ->securityOptions(
        [
            'name=apparmor',
            'name=seccomp,profile=default',
            'name=selinux',
            'name=userns'
        ]
    )
    ->serverVersion('17.06.0-ce')
    ->swapLimit(true)
    ->systemStatus(
        [
            [
                'Role',
                'primary'
            ],
            [
                'State',
                'Healthy'
            ],
            [
                'Strategy',
                'spread'
            ],
            [
                'Filters',
                'health, port, containerslots, dependency, affinity, constraint, whitelist'
            ],
            [
                'Nodes',
                '2'
            ],
            [
                ' swarm-agent-00',
                '192.168.99.102:2376'
            ],
            [
                '  └ ID',
                '5CT6:FBGO:RVGO:CZL4:PB2K:WCYN:2JSV:KSHH:GGFW:QOPG:6J5Q:IOZ2|192.168.99.102:2376'
            ],
            [
                '  └ Status',
                'Healthy'
            ],
            [
                '  └ Containers',
                '1 (1 Running, 0 Paused, 0 Stopped)'
            ],
            [
                '  └ Reserved CPUs',
                '0 / 1'
            ],
            [
                '  └ Reserved Memory',
                '0 B / 1.021 GiB'
            ],
            [
                '  └ Labels',
                'kernelversion=4.4.74-boot2docker, operatingsystem=Boot2Docker 17.06.0-ce (TCL 7.2); HEAD : 0672754 - Thu Jun 29 00:06:31 UTC 2017, ostype=linux, provider=virtualbox, storagedriver=aufs'
            ],
            [
                '  └ UpdatedAt',
                '2017-08-09T10:03:46Z'
            ],
            [
                '  └ ServerVersion',
                '17.06.0-ce'
            ],
            [
                ' swarm-manager',
                '192.168.99.101:2376'
            ],
            [
                '  └ ID',
                'TAMD:7LL3:SEF7:LW2W:4Q2X:WVFH:RTXX:JSYS:XY2P:JEHL:ZMJK:JGIW|192.168.99.101:2376'
            ],
            [
                '  └ Status',
                'Healthy'
            ],
            [
                '  └ Containers',
                '2 (2 Running, 0 Paused, 0 Stopped)'
            ],
            [
                '  └ Reserved CPUs',
                '0 / 1'
            ],
            [
                '  └ Reserved Memory',
                '0 B / 1.021 GiB'
            ],
            [
                '  └ Labels',
                'kernelversion=4.4.74-boot2docker, operatingsystem=Boot2Docker 17.06.0-ce (TCL 7.2); HEAD : 0672754 - Thu Jun 29 00:06:31 UTC 2017, ostype=linux, provider=virtualbox, storagedriver=aufs'
            ],
            [
                '  └ UpdatedAt',
                '2017-08-09T10:04:11Z'
            ],
            [
                '  └ ServerVersion',
                '17.06.0-ce'
            ]
        ]
    )
    ->systemTime('2017-08-08T20:28:29.06202363Z')
    ->build();
```

