
# Runtime

Runtime describes an [OCI compliant](https://github.com/opencontainers/runtime-spec)
runtime.

The runtime is invoked by the daemon via the `containerd` daemon. OCI
runtimes act as an interface to the Linux kernel namespaces, cgroups,
and SELinux.

## Structure

`Runtime`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `path` | `?string` | Optional | Name and, optional, path, of the OCI executable binary.<br><br>If the path is omitted, the daemon searches the host's `$PATH` for the<br>binary and uses the first result. | getPath(): ?string | setPath(?string path): void |
| `runtimeArgs` | `?(string[])` | Optional | List of command-line arguments to pass to the runtime when invoked. | getRuntimeArgs(): ?array | setRuntimeArgs(?array runtimeArgs): void |

## Example

```php
use DockerLib\Models\Builders\RuntimeBuilder;

$runtime = RuntimeBuilder::init()
    ->path('/usr/local/bin/my-oci-runtime')
    ->runtimeArgs(
        [
            '--debug',
            '--systemd-cgroup=false'
        ]
    )
    ->build();
```

