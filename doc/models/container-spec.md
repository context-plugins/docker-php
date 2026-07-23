
# Container Spec

Invalid when specified with `PluginSpec`.

## Structure

`ContainerSpec`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `args` | `?(string[])` | Optional | Arguments to the command. | getArgs(): ?array | setArgs(?array args): void |
| `command` | `?(string[])` | Optional | The command to be run in the image. | getCommand(): ?array | setCommand(?array command): void |
| `configs` | [`?(Config2[])`](../../doc/models/config-2.md) | Optional | Configs contains references to zero or more configs that will be exposed to the service. | getConfigs(): ?array | setConfigs(?array configs): void |
| `dNSConfig` | [`?DNSConfig2`](../../doc/models/dns-config-2.md) | Optional | - | getDNSConfig(): ?DNSConfig2 | setDNSConfig(?DNSConfig2 dNSConfig): void |
| `dir` | `?string` | Optional | The working directory for commands to run in. | getDir(): ?string | setDir(?string dir): void |
| `env` | `?(string[])` | Optional | A list of environment variables in the form `VAR=value`. | getEnv(): ?array | setEnv(?array env): void |
| `groups` | `?(string[])` | Optional | A list of additional groups that the container process will run as. | getGroups(): ?array | setGroups(?array groups): void |
| `healthCheck` | [`?Healthcheck`](../../doc/models/healthcheck.md) | Optional | - | getHealthCheck(): ?Healthcheck | setHealthCheck(?Healthcheck healthCheck): void |
| `hostname` | `?string` | Optional | The hostname to use for the container, as a valid RFC 1123 hostname. | getHostname(): ?string | setHostname(?string hostname): void |
| `hosts` | `?(string[])` | Optional | A list of hostname/IP mappings to add to the container's `hosts`<br>file. The format of extra hosts is specified in the<br>[hosts(5)](http://man7.org/linux/man-pages/man5/hosts.5.html)<br>man page:<br><br>    IP_address canonical_hostname [aliases...] | getHosts(): ?array | setHosts(?array hosts): void |
| `image` | `?string` | Optional | The image name to use for the container | getImage(): ?string | setImage(?string image): void |
| `labels` | `?array<string,string>` | Optional | User-defined key/value data. | getLabels(): ?array | setLabels(?array labels): void |
| `mounts` | [`?(Mount[])`](../../doc/models/mount.md) | Optional | Specification for mounts to be added to containers created as part of the service. | getMounts(): ?array | setMounts(?array mounts): void |
| `openStdin` | `?bool` | Optional | Open `stdin` | getOpenStdin(): ?bool | setOpenStdin(?bool openStdin): void |
| `privileges` | [`?Privileges2`](../../doc/models/privileges-2.md) | Optional | - | getPrivileges(): ?Privileges2 | setPrivileges(?Privileges2 privileges): void |
| `readOnly` | `?bool` | Optional | Mount the container's root filesystem as read only. | getReadOnly(): ?bool | setReadOnly(?bool readOnly): void |
| `secrets` | [`?(Secret1[])`](../../doc/models/secret-1.md) | Optional | Secrets contains references to zero or more secrets that will be exposed to the service. | getSecrets(): ?array | setSecrets(?array secrets): void |
| `stopGracePeriod` | `?int` | Optional | Amount of time to wait for the container to terminate before forcefully killing it. | getStopGracePeriod(): ?int | setStopGracePeriod(?int stopGracePeriod): void |
| `stopSignal` | `?string` | Optional | Signal to stop the container. | getStopSignal(): ?string | setStopSignal(?string stopSignal): void |
| `tTY` | `?bool` | Optional | Whether a pseudo-TTY should be allocated. | getTTY(): ?bool | setTTY(?bool tTY): void |
| `user` | `?string` | Optional | The user inside the container. | getUser(): ?string | setUser(?string user): void |

## Example

```php
use DockerLib\Models\Builders\ContainerSpecBuilder;
use DockerLib\Models\Builders\Config2Builder;
use DockerLib\Models\Builders\File1Builder;
use DockerLib\Models\Builders\DNSConfig2Builder;

$containerSpec = ContainerSpecBuilder::init()
    ->args(
        [
            'Args8'
        ]
    )
    ->command(
        [
            'Command8',
            'Command7',
            'Command6'
        ]
    )
    ->configs(
        [
            Config2Builder::init()
                ->configID('ConfigID0')
                ->configName('ConfigName2')
                ->file(
                    File1Builder::init()
                        ->gID('GID0')
                        ->mode(224)
                        ->name('Name0')
                        ->uID('UID0')
                        ->build()
                )
                ->build()
        ]
    )
    ->dNSConfig(
        DNSConfig2Builder::init()
            ->nameservers(
                [
                    'Nameservers4',
                    'Nameservers3'
                ]
            )
            ->options(
                [
                    'Options6'
                ]
            )
            ->search(
                [
                    'Search7'
                ]
            )
            ->build()
    )
    ->dir('Dir4')
    ->build();
```

