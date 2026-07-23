
# Containers Exec Request

## Structure

`ContainersExecRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `attachStderr` | `?bool` | Optional | Attach to `stderr` of the exec command. | getAttachStderr(): ?bool | setAttachStderr(?bool attachStderr): void |
| `attachStdin` | `?bool` | Optional | Attach to `stdin` of the exec command. | getAttachStdin(): ?bool | setAttachStdin(?bool attachStdin): void |
| `attachStdout` | `?bool` | Optional | Attach to `stdout` of the exec command. | getAttachStdout(): ?bool | setAttachStdout(?bool attachStdout): void |
| `cmd` | `?(string[])` | Optional | Command to run, as a string or array of strings. | getCmd(): ?array | setCmd(?array cmd): void |
| `detachKeys` | `?string` | Optional | Override the key sequence for detaching a container. Format is a single character `[a-Z]` or `ctrl-<value>` where `<value>` is one of: `a-z`, `@`, `^`, `[`, `,` or `_`. | getDetachKeys(): ?string | setDetachKeys(?string detachKeys): void |
| `env` | `?(string[])` | Optional | A list of environment variables in the form `["VAR=value", ...]`. | getEnv(): ?array | setEnv(?array env): void |
| `privileged` | `?bool` | Optional | Runs the exec process with extended privileges.<br><br>**Default**: `false` | getPrivileged(): ?bool | setPrivileged(?bool privileged): void |
| `tty` | `?bool` | Optional | Allocate a pseudo-TTY. | getTty(): ?bool | setTty(?bool tty): void |
| `user` | `?string` | Optional | The user, and optionally, group to run the exec process inside the container. Format is one of: `user`, `user:group`, `uid`, or `uid:gid`. | getUser(): ?string | setUser(?string user): void |

## Example

```php
use DockerLib\Models\Builders\ContainersExecRequestBuilder;

$containersExecRequest = ContainersExecRequestBuilder::init()
    ->attachStderr(true)
    ->attachStdin(false)
    ->attachStdout(true)
    ->cmd(
        [
            'date'
        ]
    )
    ->detachKeys('ctrl-p,ctrl-q')
    ->env(
        [
            'FOO=bar',
            'BAZ=quux'
        ]
    )
    ->tty(false)
    ->build();
```

