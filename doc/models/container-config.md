
# Container Config

Configuration for a container that is portable between hosts

## Structure

`ContainerConfig`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `argsEscaped` | `?bool` | Optional | Command is already escaped (Windows only) | getArgsEscaped(): ?bool | setArgsEscaped(?bool argsEscaped): void |
| `attachStderr` | `?bool` | Optional | Whether to attach to `stderr`.<br><br>**Default**: `true` | getAttachStderr(): ?bool | setAttachStderr(?bool attachStderr): void |
| `attachStdin` | `?bool` | Optional | Whether to attach to `stdin`.<br><br>**Default**: `false` | getAttachStdin(): ?bool | setAttachStdin(?bool attachStdin): void |
| `attachStdout` | `?bool` | Optional | Whether to attach to `stdout`.<br><br>**Default**: `true` | getAttachStdout(): ?bool | setAttachStdout(?bool attachStdout): void |
| `cmd` | array[]\|string\|null | Optional | This is a container for one-of cases. | getCmd(): | setCmd( cmd): void |
| `domainname` | `?string` | Optional | The domain name to use for the container. | getDomainname(): ?string | setDomainname(?string domainname): void |
| `entrypoint` | array[]\|string\|null | Optional | This is a container for one-of cases. | getEntrypoint(): | setEntrypoint( entrypoint): void |
| `env` | `?(string[])` | Optional | A list of environment variables to set inside the container in the form `["VAR=value", ...]`. A variable without `=` is removed from the environment, rather than to have an empty value. | getEnv(): ?array | setEnv(?array env): void |
| `exposedPorts` | [`?array<string,string(ExposedPortsEnum)>`](../../doc/models/exposed-ports-enum.md) | Optional | An object mapping ports to an empty object in the form:<br><br>`{"<port>/<tcp\|udp>": {}}` | getExposedPorts(): ?array | setExposedPorts(?array exposedPorts): void |
| `healthcheck` | [`?Healthcheck`](../../doc/models/healthcheck.md) | Optional | - | getHealthcheck(): ?Healthcheck | setHealthcheck(?Healthcheck healthcheck): void |
| `hostname` | `?string` | Optional | The hostname to use for the container, as a valid RFC 1123 hostname. | getHostname(): ?string | setHostname(?string hostname): void |
| `image` | `?string` | Optional | The name of the image to use when creating the container | getImage(): ?string | setImage(?string image): void |
| `labels` | `?array<string,string>` | Optional | User-defined key/value metadata. | getLabels(): ?array | setLabels(?array labels): void |
| `macAddress` | `?string` | Optional | MAC address of the container. | getMacAddress(): ?string | setMacAddress(?string macAddress): void |
| `networkDisabled` | `?bool` | Optional | Disable networking for the container. | getNetworkDisabled(): ?bool | setNetworkDisabled(?bool networkDisabled): void |
| `onBuild` | `?(string[])` | Optional | `ONBUILD` metadata that were defined in the image's `Dockerfile`. | getOnBuild(): ?array | setOnBuild(?array onBuild): void |
| `openStdin` | `?bool` | Optional | Open `stdin`<br><br>**Default**: `false` | getOpenStdin(): ?bool | setOpenStdin(?bool openStdin): void |
| `shell` | `?(string[])` | Optional | Shell for when `RUN`, `CMD`, and `ENTRYPOINT` uses a shell. | getShell(): ?array | setShell(?array shell): void |
| `stdinOnce` | `?bool` | Optional | Close `stdin` after one attached client disconnects<br><br>**Default**: `false` | getStdinOnce(): ?bool | setStdinOnce(?bool stdinOnce): void |
| `stopSignal` | `?string` | Optional | Signal to stop a container as a string or unsigned integer.<br><br>**Default**: `'SIGTERM'` | getStopSignal(): ?string | setStopSignal(?string stopSignal): void |
| `stopTimeout` | `?int` | Optional | Timeout to stop a container in seconds.<br><br>**Default**: `10` | getStopTimeout(): ?int | setStopTimeout(?int stopTimeout): void |
| `tty` | `?bool` | Optional | Attach standard streams to a TTY, including `stdin` if it is not closed.<br><br>**Default**: `false` | getTty(): ?bool | setTty(?bool tty): void |
| `user` | `?string` | Optional | The user that commands are run as inside the container. | getUser(): ?string | setUser(?string user): void |
| `volumes` | [`?Volumes1`](../../doc/models/volumes-1.md) | Optional | - | getVolumes(): ?Volumes1 | setVolumes(?Volumes1 volumes): void |
| `workingDir` | `?string` | Optional | The working directory for commands to run in. | getWorkingDir(): ?string | setWorkingDir(?string workingDir): void |

## Example

```php
use DockerLib\Models\Builders\ContainerConfigBuilder;
use DockerLib\ApiHelper;

$containerConfig = ContainerConfigBuilder::init()
    ->argsEscaped(false)
    ->attachStderr(true)
    ->attachStdin(false)
    ->attachStdout(true)
    ->cmd(
        [
            ApiHelper::deserialize('{"key1":"val1","key2":"val2"}')
        ]
    )
    ->openStdin(false)
    ->stdinOnce(false)
    ->stopSignal('SIGTERM')
    ->stopTimeout(10)
    ->tty(false)
    ->build();
```

