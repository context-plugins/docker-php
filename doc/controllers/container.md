# Container

Create and manage containers.

```php
$containerController = $client->getContainerController();
```

## Class Name

`ContainerController`

## Methods

* [Container Create](../../doc/controllers/container.md#container-create)
* [Container List](../../doc/controllers/container.md#container-list)
* [Container Prune](../../doc/controllers/container.md#container-prune)
* [Container Delete](../../doc/controllers/container.md#container-delete)
* [Container Archive](../../doc/controllers/container.md#container-archive)
* [Put Container Archive](../../doc/controllers/container.md#put-container-archive)
* [Container Attach](../../doc/controllers/container.md#container-attach)
* [Container Attach Websocket](../../doc/controllers/container.md#container-attach-websocket)
* [Container Changes](../../doc/controllers/container.md#container-changes)
* [Container Export](../../doc/controllers/container.md#container-export)
* [Container Inspect](../../doc/controllers/container.md#container-inspect)
* [Container Kill](../../doc/controllers/container.md#container-kill)
* [Container Logs](../../doc/controllers/container.md#container-logs)
* [Container Pause](../../doc/controllers/container.md#container-pause)
* [Container Rename](../../doc/controllers/container.md#container-rename)
* [Container Resize](../../doc/controllers/container.md#container-resize)
* [Container Restart](../../doc/controllers/container.md#container-restart)
* [Container Start](../../doc/controllers/container.md#container-start)
* [Container Stats](../../doc/controllers/container.md#container-stats)
* [Container Stop](../../doc/controllers/container.md#container-stop)
* [Container Top](../../doc/controllers/container.md#container-top)
* [Container Unpause](../../doc/controllers/container.md#container-unpause)
* [Container Update](../../doc/controllers/container.md#container-update)
* [Container Wait](../../doc/controllers/container.md#container-wait)


# Container Create

```php
function containerCreate(ContainersCreateRequest $body, ?string $name = null): ContainersCreateResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`ContainersCreateRequest`](../../doc/models/containers-create-request.md) | Body, Required | Container to create |
| `name` | `?string` | Query, Optional | Assign the specified name to the container. Must match `/?[a-zA-Z0-9_-]+`.<br><br>**Constraints**: *Pattern*: `/?[a-zA-Z0-9_-]+` |

## Response Type

**201**: Container created successfully

[`ContainersCreateResponse`](../../doc/models/containers-create-response.md)

## Example Usage

```php
$body = ContainersCreateRequestBuilder::init()
    ->attachStderr(true)
    ->attachStdin(false)
    ->attachStdout(true)
    ->openStdin(false)
    ->stdinOnce(false)
    ->stopSignal('SIGTERM')
    ->stopTimeout(10)
    ->tty(false)
    ->build();

$containerController = $client->getContainerController();

try {
    $result = $containerController->containerCreate($body);
    echo 'ContainersCreateResponse:';
    var_dump($result);
} catch (ContainersCreate400ErrorException $exp) {
    echo 'Caught ContainersCreate400ErrorException:', $exp;
} catch (ContainersCreate404ErrorException $exp) {
    echo 'Caught ContainersCreate404ErrorException:', $exp;
} catch (ContainersCreate409ErrorException $exp) {
    echo 'Caught ContainersCreate409ErrorException:', $exp;
} catch (ContainersCreate500ErrorException $exp) {
    echo 'Caught ContainersCreate500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "Id": "e90e34656806",
  "Warnings": []
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | bad parameter | [`ContainersCreate400ErrorException`](../../doc/models/containers-create-400-error-exception.md) |
| 404 | no such container | [`ContainersCreate404ErrorException`](../../doc/models/containers-create-404-error-exception.md) |
| 409 | conflict | [`ContainersCreate409ErrorException`](../../doc/models/containers-create-409-error-exception.md) |
| 500 | server error | [`ContainersCreate500ErrorException`](../../doc/models/containers-create-500-error-exception.md) |


# Container List

Returns a list of containers. For details on the format, see [the inspect endpoint](#operation/ContainerInspect).

Note that it uses a different, smaller representation of a container than inspecting a single container. For example,
the list of linked containers is not propagated .

```php
function containerList(
    ?bool $all = false,
    ?int $limit = null,
    ?bool $size = false,
    ?string $filters = null
): array
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `all` | `?bool` | Query, Optional | Return all containers. By default, only running containers are shown<br><br>**Default**: `false` |
| `limit` | `?int` | Query, Optional | Return this number of most recently created containers, including non-running ones. |
| `size` | `?bool` | Query, Optional | Return the size of container as fields `SizeRw` and `SizeRootFs`.<br><br>**Default**: `false` |
| `filters` | `?string` | Query, Optional | Filters to process on the container list, encoded as JSON (a `map[string][]string`). For example, `{"status": ["paused"]}` will only return paused containers. Available filters:<br><br>- `ancestor`=(`<image-name>[:<tag>]`, `<image id>`, or `<image@digest>`)<br>- `before`=(`<container id>` or `<container name>`)<br>- `expose`=(`<port>[/<proto>]`\|`<startport-endport>/[<proto>]`)<br>- `exited=<int>` containers with exit code of `<int>`<br>- `health`=(`starting`\|`healthy`\|`unhealthy`\|`none`)<br>- `id=<ID>` a container's ID<br>- `isolation=`(`default`\|`process`\|`hyperv`) (Windows daemon only)<br>- `is-task=`(`true`\|`false`)<br>- `label=key` or `label="key=value"` of a container label<br>- `name=<name>` a container's name<br>- `network`=(`<network id>` or `<network name>`)<br>- `publish`=(`<port>[/<proto>]`\|`<startport-endport>/[<proto>]`)<br>- `since`=(`<container id>` or `<container name>`)<br>- `status=`(`created`\|`restarting`\|`running`\|`removing`\|`paused`\|`exited`\|`dead`)<br>- `volume`=(`<volume name>` or `<mount point destination>`) |

## Response Type

**200**: no error

[`ContainerSummary[]`](../../doc/models/container-summary.md)

## Example Usage

```php
$all = false;

$size = false;

$containerController = $client->getContainerController();

try {
    $result = $containerController->containerList(
        $all,
        null,
        $size
    );
    echo 'ContainerSummary[]:';
    var_dump($result);
} catch (ContainersJson400ErrorException $exp) {
    echo 'Caught ContainersJson400ErrorException:', $exp;
} catch (ContainersJson500ErrorException $exp) {
    echo 'Caught ContainersJson500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
[
  {
    "Command": "echo 1",
    "Created": 1367854155,
    "HostConfig": {
      "NetworkMode": "default"
    },
    "Id": "8dfafdbc3a40",
    "Image": "ubuntu:latest",
    "ImageID": "d74508fb6632491cea586a1fd7d748dfc5274cd6fdfedee309ecdcbc2bf5cb82",
    "Labels": {
      "com.example.license": "GPL",
      "com.example.vendor": "Acme",
      "com.example.version": "1.0"
    },
    "Mounts": [
      {
        "Destination": "/data",
        "Driver": "local",
        "Mode": "ro,Z",
        "Name": "fac362...80535",
        "Propagation": "",
        "RW": false,
        "Source": "/data"
      }
    ],
    "Names": [
      "/boring_feynman"
    ],
    "NetworkSettings": {
      "Networks": {
        "bridge": {
          "EndpointID": "2cdc4edb1ded3631c81f57966563e5c8525b81121bb3706a9a9a3ae102711f3f",
          "Gateway": "172.17.0.1",
          "GlobalIPv6Address": "",
          "GlobalIPv6PrefixLen": 0,
          "IPAddress": "172.17.0.2",
          "IPPrefixLen": 16,
          "IPv6Gateway": "",
          "MacAddress": "02:42:ac:11:00:02",
          "NetworkID": "7ea29fc1412292a2d7bba362f9253545fecdfa8ce9a6e37dd10ba8bee7129812"
        }
      }
    },
    "Ports": [
      {
        "PrivatePort": 2222,
        "PublicPort": 3333,
        "Type": "tcp"
      }
    ],
    "SizeRootFs": 0,
    "SizeRw": 12288,
    "State": "Exited",
    "Status": "Exit 0"
  },
  {
    "Command": "echo 222222",
    "Created": 1367854155,
    "HostConfig": {
      "NetworkMode": "default"
    },
    "Id": "9cd87474be90",
    "Image": "ubuntu:latest",
    "ImageID": "d74508fb6632491cea586a1fd7d748dfc5274cd6fdfedee309ecdcbc2bf5cb82",
    "Labels": {},
    "Mounts": [],
    "Names": [
      "/coolName"
    ],
    "NetworkSettings": {
      "Networks": {
        "bridge": {
          "EndpointID": "88eaed7b37b38c2a3f0c4bc796494fdf51b270c2d22656412a2ca5d559a64d7a",
          "Gateway": "172.17.0.1",
          "GlobalIPv6Address": "",
          "GlobalIPv6PrefixLen": 0,
          "IPAddress": "172.17.0.8",
          "IPPrefixLen": 16,
          "IPv6Gateway": "",
          "MacAddress": "02:42:ac:11:00:08",
          "NetworkID": "7ea29fc1412292a2d7bba362f9253545fecdfa8ce9a6e37dd10ba8bee7129812"
        }
      }
    },
    "Ports": [],
    "SizeRootFs": 0,
    "SizeRw": 12288,
    "State": "Exited",
    "Status": "Exit 0"
  },
  {
    "Command": "echo 3333333333333333",
    "Created": 1367854154,
    "HostConfig": {
      "NetworkMode": "default"
    },
    "Id": "3176a2479c92",
    "Image": "ubuntu:latest",
    "ImageID": "d74508fb6632491cea586a1fd7d748dfc5274cd6fdfedee309ecdcbc2bf5cb82",
    "Labels": {},
    "Mounts": [],
    "Names": [
      "/sleepy_dog"
    ],
    "NetworkSettings": {
      "Networks": {
        "bridge": {
          "EndpointID": "8b27c041c30326d59cd6e6f510d4f8d1d570a228466f956edf7815508f78e30d",
          "Gateway": "172.17.0.1",
          "GlobalIPv6Address": "",
          "GlobalIPv6PrefixLen": 0,
          "IPAddress": "172.17.0.6",
          "IPPrefixLen": 16,
          "IPv6Gateway": "",
          "MacAddress": "02:42:ac:11:00:06",
          "NetworkID": "7ea29fc1412292a2d7bba362f9253545fecdfa8ce9a6e37dd10ba8bee7129812"
        }
      }
    },
    "Ports": [],
    "SizeRootFs": 0,
    "SizeRw": 12288,
    "State": "Exited",
    "Status": "Exit 0"
  },
  {
    "Command": "echo 444444444444444444444444444444444",
    "Created": 1367854152,
    "HostConfig": {
      "NetworkMode": "default"
    },
    "Id": "4cb07b47f9fb",
    "Image": "ubuntu:latest",
    "ImageID": "d74508fb6632491cea586a1fd7d748dfc5274cd6fdfedee309ecdcbc2bf5cb82",
    "Labels": {},
    "Mounts": [],
    "Names": [
      "/running_cat"
    ],
    "NetworkSettings": {
      "Networks": {
        "bridge": {
          "EndpointID": "d91c7b2f0644403d7ef3095985ea0e2370325cd2332ff3a3225c4247328e66e9",
          "Gateway": "172.17.0.1",
          "GlobalIPv6Address": "",
          "GlobalIPv6PrefixLen": 0,
          "IPAddress": "172.17.0.5",
          "IPPrefixLen": 16,
          "IPv6Gateway": "",
          "MacAddress": "02:42:ac:11:00:05",
          "NetworkID": "7ea29fc1412292a2d7bba362f9253545fecdfa8ce9a6e37dd10ba8bee7129812"
        }
      }
    },
    "Ports": [],
    "SizeRootFs": 0,
    "SizeRw": 12288,
    "State": "Exited",
    "Status": "Exit 0"
  }
]
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | bad parameter | [`ContainersJson400ErrorException`](../../doc/models/containers-json-400-error-exception.md) |
| 500 | server error | [`ContainersJson500ErrorException`](../../doc/models/containers-json-500-error-exception.md) |


# Container Prune

```php
function containerPrune(?string $filters = null): ContainersPruneResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `filters` | `?string` | Query, Optional | Filters to process on the prune list, encoded as JSON (a `map[string][]string`).<br><br>Available filters:<br><br>- `until=<timestamp>` Prune containers created before this timestamp. The `<timestamp>` can be Unix timestamps, date formatted timestamps, or Go duration strings (e.g. `10m`, `1h30m`) computed relative to the daemon machine’s time.<br>- `label` (`label=<key>`, `label=<key>=<value>`, `label!=<key>`, or `label!=<key>=<value>`) Prune containers with (or without, in case `label!=...` is used) the specified labels. |

## Response Type

**200**: No error

[`ContainersPruneResponse`](../../doc/models/containers-prune-response.md)

## Example Usage

```php
$containerController = $client->getContainerController();

try {
    $result = $containerController->containerPrune();
    echo 'ContainersPruneResponse:';
    var_dump($result);
} catch (ContainersPrune500ErrorException $exp) {
    echo 'Caught ContainersPrune500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | Server error | [`ContainersPrune500ErrorException`](../../doc/models/containers-prune-500-error-exception.md) |


# Container Delete

```php
function containerDelete(string $id, ?bool $v = false, ?bool $force = false, ?bool $link = false): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID or name of the container |
| `v` | `?bool` | Query, Optional | Remove the volumes associated with the container.<br><br>**Default**: `false` |
| `force` | `?bool` | Query, Optional | If the container is running, kill it before removing it.<br><br>**Default**: `false` |
| `link` | `?bool` | Query, Optional | Remove the specified link associated with the container.<br><br>**Default**: `false` |

## Response Type

**204**: no error

`void`

## Example Usage

```php
$id = 'id0';

$v = false;

$force = false;

$link = false;

$containerController = $client->getContainerController();

try {
    $containerController->containerDelete(
        $id,
        $v,
        $force,
        $link
    );
} catch (Containers400ErrorException $exp) {
    echo 'Caught Containers400ErrorException:', $exp;
} catch (Containers404ErrorException $exp) {
    echo 'Caught Containers404ErrorException:', $exp;
} catch (Containers409ErrorException $exp) {
    echo 'Caught Containers409ErrorException:', $exp;
} catch (Containers500ErrorException $exp) {
    echo 'Caught Containers500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | bad parameter | [`Containers400ErrorException`](../../doc/models/containers-400-error-exception.md) |
| 404 | no such container | [`Containers404ErrorException`](../../doc/models/containers-404-error-exception.md) |
| 409 | conflict | [`Containers409ErrorException`](../../doc/models/containers-409-error-exception.md) |
| 500 | server error | [`Containers500ErrorException`](../../doc/models/containers-500-error-exception.md) |


# Container Archive

Get a tar archive of a resource in the filesystem of container id.

```php
function containerArchive(string $id, string $path): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID or name of the container |
| `path` | `string` | Query, Required | Resource in the container’s filesystem to archive. |

## Response Type

**200**: no error

`void`

## Example Usage

```php
$id = 'id0';

$path = 'path6';

$containerController = $client->getContainerController();

try {
    $containerController->containerArchive(
        $id,
        $path
    );
} catch (ContainersArchive404ErrorException $exp) {
    echo 'Caught ContainersArchive404ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad parameter | `ApiException` |
| 404 | Container or path does not exist | [`ContainersArchive404ErrorException`](../../doc/models/containers-archive-404-error-exception.md) |
| 500 | server error | `ApiException` |


# Put Container Archive

Upload a tar archive to be extracted to a path in the filesystem of container id.

```php
function putContainerArchive(
    string $id,
    string $path,
    string $contentType,
    FileWrapper $body,
    ?string $noOverwriteDirNonDir = null
): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID or name of the container |
| `path` | `string` | Query, Required | Path to a directory in the container to extract the archive’s contents into. |
| `contentType` | [`string(ContentType1Enum)`](../../doc/models/content-type-1-enum.md) | Header, Required | - |
| `body` | [`FileWrapper`](../../doc/models/file.md) | Form, Required | The input stream must be a tar archive compressed with one of the following algorithms: identity (no compression), gzip, bzip2, xz. |
| `noOverwriteDirNonDir` | `?string` | Query, Optional | If “1”, “true”, or “True” then it will be an error if unpacking the given content would cause an existing directory to be replaced with a non-directory and vice versa. |

## Response Type

**200**: The content was extracted successfully

`void`

## Example Usage

```php
$id = 'id0';

$path = 'path6';

$contentType = ContentType1Enum::ENUM_APPLICATIONOCTETSTREAM;

$body = FileWrapper::createFromPath('dummy_file');

$containerController = $client->getContainerController();

try {
    $containerController->putContainerArchive(
        $id,
        $path,
        $contentType,
        $body
    );
} catch (ContainersArchive400ErrorException $exp) {
    echo 'Caught ContainersArchive400ErrorException:', $exp;
} catch (ContainersArchive403ErrorException $exp) {
    echo 'Caught ContainersArchive403ErrorException:', $exp;
} catch (ContainersArchive404Error2Exception $exp) {
    echo 'Caught ContainersArchive404Error2Exception:', $exp;
} catch (ContainersArchive500ErrorException $exp) {
    echo 'Caught ContainersArchive500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad parameter | [`ContainersArchive400ErrorException`](../../doc/models/containers-archive-400-error-exception.md) |
| 403 | Permission denied, the volume or container rootfs is marked as read-only. | [`ContainersArchive403ErrorException`](../../doc/models/containers-archive-403-error-exception.md) |
| 404 | No such container or path does not exist inside the container | [`ContainersArchive404Error2Exception`](../../doc/models/containers-archive-404-error-2-exception.md) |
| 500 | Server error | [`ContainersArchive500ErrorException`](../../doc/models/containers-archive-500-error-exception.md) |


# Container Attach

Attach to a container to read its output or send it input. You can attach to the same container multiple times and you can reattach to containers that have been detached.

Either the `stream` or `logs` parameter must be `true` for this endpoint to do anything.

See [the documentation for the `docker attach` command](https://docs.docker.com/engine/reference/commandline/attach/) for more details.

### Hijacking

This endpoint hijacks the HTTP connection to transport `stdin`, `stdout`, and `stderr` on the same socket.

This is the response from the daemon for an attach request:

```
HTTP/1.1 200 OK
Content-Type: application/vnd.docker.raw-stream

[STREAM]
```

After the headers and two new lines, the TCP connection can now be used for raw, bidirectional communication between the client and server.

To hint potential proxies about connection hijacking, the Docker client can also optionally send connection upgrade headers.

For example, the client sends this request to upgrade the connection:

```
POST /containers/16253994b7c4/attach?stream=1&stdout=1 HTTP/1.1
Upgrade: tcp
Connection: Upgrade
```

The Docker daemon will respond with a `101 UPGRADED` response, and will similarly follow with the raw stream:

```
HTTP/1.1 101 UPGRADED
Content-Type: application/vnd.docker.raw-stream
Connection: Upgrade
Upgrade: tcp

[STREAM]
```

### Stream format

When the TTY setting is disabled in [`POST /containers/create`](#operation/ContainerCreate), the stream over the hijacked connected is multiplexed to separate out `stdout` and `stderr`. The stream consists of a series of frames, each containing a header and a payload.

The header contains the information which the stream writes (`stdout` or `stderr`). It also contains the size of the associated frame encoded in the last four bytes (`uint32`).

It is encoded on the first eight bytes like this:

```go
header := [8]byte{STREAM_TYPE, 0, 0, 0, SIZE1, SIZE2, SIZE3, SIZE4}
```

`STREAM_TYPE` can be:

- 0: `stdin` (is written on `stdout`)
- 1: `stdout`
- 2: `stderr`

`SIZE1, SIZE2, SIZE3, SIZE4` are the four bytes of the `uint32` size encoded as big endian.

Following the header is the payload, which is the specified number of bytes of `STREAM_TYPE`.

The simplest way to implement this protocol is the following:

1. Read 8 bytes.
2. Choose `stdout` or `stderr` depending on the first byte.
3. Extract the frame size from the last four bytes.
4. Read the extracted size and output it on the correct output.
5. Goto 1.

### Stream format when using a TTY

When the TTY setting is enabled in [`POST /containers/create`](#operation/ContainerCreate), the stream is not multiplexed. The data exchanged over the hijacked connection is simply the raw data from the process PTY and client's `stdin`.

```php
function containerAttach(
    string $id,
    ?string $detachKeys = null,
    ?bool $logs = false,
    ?bool $stream = false,
    ?bool $stdin = false,
    ?bool $stdout = false,
    ?bool $stderr = false
): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID or name of the container |
| `detachKeys` | `?string` | Query, Optional | Override the key sequence for detaching a container.Format is a single character `[a-Z]` or `ctrl-<value>` where `<value>` is one of: `a-z`, `@`, `^`, `[`, `,` or `_`. |
| `logs` | `?bool` | Query, Optional | Replay previous logs from the container.<br><br>This is useful for attaching to a container that has started and you want to output everything since the container started.<br><br>If `stream` is also enabled, once all the previous output has been returned, it will seamlessly transition into streaming current output.<br><br>**Default**: `false` |
| `stream` | `?bool` | Query, Optional | Stream attached streams from the time the request was made onwards<br><br>**Default**: `false` |
| `stdin` | `?bool` | Query, Optional | Attach to `stdin`<br><br>**Default**: `false` |
| `stdout` | `?bool` | Query, Optional | Attach to `stdout`<br><br>**Default**: `false` |
| `stderr` | `?bool` | Query, Optional | Attach to `stderr`<br><br>**Default**: `false` |

## Response Type

**200**: no error, no upgrade header found

`void`

## Example Usage

```php
$id = 'id0';

$logs = false;

$stream = false;

$stdin = false;

$stdout = false;

$stderr = false;

$containerController = $client->getContainerController();

try {
    $containerController->containerAttach(
        $id,
        null,
        $logs,
        $stream,
        $stdin,
        $stdout,
        $stderr
    );
} catch (ContainersAttach404ErrorException $exp) {
    echo 'Caught ContainersAttach404ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | bad parameter | `ApiException` |
| 404 | no such container | [`ContainersAttach404ErrorException`](../../doc/models/containers-attach-404-error-exception.md) |
| 500 | server error | `ApiException` |


# Container Attach Websocket

```php
function containerAttachWebsocket(
    string $id,
    ?string $detachKeys = null,
    ?bool $logs = false,
    ?bool $stream = false,
    ?bool $stdin = false,
    ?bool $stdout = false,
    ?bool $stderr = false
): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID or name of the container |
| `detachKeys` | `?string` | Query, Optional | Override the key sequence for detaching a container.Format is a single character `[a-Z]` or `ctrl-<value>` where `<value>` is one of: `a-z`, `@`, `^`, `[`, `,`, or `_`. |
| `logs` | `?bool` | Query, Optional | Return logs<br><br>**Default**: `false` |
| `stream` | `?bool` | Query, Optional | Return stream<br><br>**Default**: `false` |
| `stdin` | `?bool` | Query, Optional | Attach to `stdin`<br><br>**Default**: `false` |
| `stdout` | `?bool` | Query, Optional | Attach to `stdout`<br><br>**Default**: `false` |
| `stderr` | `?bool` | Query, Optional | Attach to `stderr`<br><br>**Default**: `false` |

## Response Type

**200**: no error, no upgrade header found

`void`

## Example Usage

```php
$id = 'id0';

$logs = false;

$stream = false;

$stdin = false;

$stdout = false;

$stderr = false;

$containerController = $client->getContainerController();

try {
    $containerController->containerAttachWebsocket(
        $id,
        null,
        $logs,
        $stream,
        $stdin,
        $stdout,
        $stderr
    );
} catch (ContainersAttachWs400ErrorException $exp) {
    echo 'Caught ContainersAttachWs400ErrorException:', $exp;
} catch (ContainersAttachWs404ErrorException $exp) {
    echo 'Caught ContainersAttachWs404ErrorException:', $exp;
} catch (ContainersAttachWs500ErrorException $exp) {
    echo 'Caught ContainersAttachWs500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | bad parameter | [`ContainersAttachWs400ErrorException`](../../doc/models/containers-attach-ws-400-error-exception.md) |
| 404 | no such container | [`ContainersAttachWs404ErrorException`](../../doc/models/containers-attach-ws-404-error-exception.md) |
| 500 | server error | [`ContainersAttachWs500ErrorException`](../../doc/models/containers-attach-ws-500-error-exception.md) |


# Container Changes

Returns which files in a container's filesystem have been added, deleted,
or modified. The `Kind` of modification can be one of:

- `0`: Modified
- `1`: Added
- `2`: Deleted

```php
function containerChanges(string $id): array
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID or name of the container |

## Response Type

**200**: The list of changes

[`ContainersChangesResponse[]`](../../doc/models/containers-changes-response.md)

## Example Usage

```php
$id = 'id0';

$containerController = $client->getContainerController();

try {
    $result = $containerController->containerChanges($id);
    echo 'ContainersChangesResponse[]:';
    var_dump($result);
} catch (ContainersChanges404ErrorException $exp) {
    echo 'Caught ContainersChanges404ErrorException:', $exp;
} catch (ContainersChanges500ErrorException $exp) {
    echo 'Caught ContainersChanges500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
[
  {
    "Kind": 0,
    "Path": "/dev"
  },
  {
    "Kind": 1,
    "Path": "/dev/kmsg"
  },
  {
    "Kind": 1,
    "Path": "/test"
  }
]
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | no such container | [`ContainersChanges404ErrorException`](../../doc/models/containers-changes-404-error-exception.md) |
| 500 | server error | [`ContainersChanges500ErrorException`](../../doc/models/containers-changes-500-error-exception.md) |


# Container Export

Export the contents of a container as a tarball.

```php
function containerExport(string $id): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID or name of the container |

## Response Type

**200**: no error

`void`

## Example Usage

```php
$id = 'id0';

$containerController = $client->getContainerController();

try {
    $containerController->containerExport($id);
} catch (ContainersExport404ErrorException $exp) {
    echo 'Caught ContainersExport404ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | no such container | [`ContainersExport404ErrorException`](../../doc/models/containers-export-404-error-exception.md) |
| 500 | server error | `ApiException` |


# Container Inspect

Return low-level information about a container.

```php
function containerInspect(string $id, ?bool $size = false): ContainersJsonResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID or name of the container |
| `size` | `?bool` | Query, Optional | Return the size of container as fields `SizeRw` and `SizeRootFs`<br><br>**Default**: `false` |

## Response Type

**200**: no error

[`ContainersJsonResponse`](../../doc/models/containers-json-response.md)

## Example Usage

```php
$id = 'id0';

$size = false;

$containerController = $client->getContainerController();

try {
    $result = $containerController->containerInspect(
        $id,
        $size
    );
    echo 'ContainersJsonResponse:';
    var_dump($result);
} catch (ContainersJson404ErrorException $exp) {
    echo 'Caught ContainersJson404ErrorException:', $exp;
} catch (ContainersJson500ErrorException $exp) {
    echo 'Caught ContainersJson500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "AppArmorProfile": "",
  "Args": [
    "-c",
    "exit 9"
  ],
  "Config": {
    "AttachStderr": true,
    "AttachStdin": false,
    "AttachStdout": true,
    "Cmd": [
      "/bin/sh",
      "-c",
      "exit 9"
    ],
    "Domainname": "",
    "Env": [
      "PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
    ],
    "Hostname": "ba033ac44011",
    "Image": "ubuntu",
    "Labels": {
      "com.example.license": "GPL",
      "com.example.vendor": "Acme",
      "com.example.version": "1.0"
    },
    "MacAddress": "",
    "NetworkDisabled": false,
    "OpenStdin": false,
    "StdinOnce": false,
    "StopSignal": "SIGTERM",
    "StopTimeout": 10,
    "Tty": false,
    "User": "",
    "Volumes": {
      "/volumes/data": {}
    },
    "WorkingDir": ""
  },
  "Created": "2015-01-06T15:47:31.485331387Z",
  "Driver": "devicemapper",
  "HostConfig": {
    "BlkioDeviceReadBps": [
      {}
    ],
    "BlkioDeviceReadIOps": [
      {}
    ],
    "BlkioDeviceWriteBps": [
      {}
    ],
    "BlkioDeviceWriteIOps": [
      {}
    ],
    "BlkioWeight": 0,
    "BlkioWeightDevice": [
      {}
    ],
    "ContainerIDFile": "",
    "CpuPercent": 80,
    "CpuPeriod": 100000,
    "CpuRealtimePeriod": 1000000,
    "CpuRealtimeRuntime": 10000,
    "CpuShares": 0,
    "CpusetCpus": "",
    "CpusetMems": "",
    "Devices": [],
    "IpcMode": "",
    "KernelMemory": 0,
    "LogConfig": {
      "Type": "json-file"
    },
    "LxcConf": [],
    "MaximumIOBps": 0,
    "MaximumIOps": 0,
    "Memory": 0,
    "MemoryReservation": 0,
    "MemorySwap": 0,
    "NetworkMode": "bridge",
    "OomKillDisable": false,
    "OomScoreAdj": 500,
    "PidMode": "",
    "PortBindings": {},
    "Privileged": false,
    "PublishAllPorts": false,
    "ReadonlyRootfs": false,
    "RestartPolicy": {
      "MaximumRetryCount": 2,
      "Name": "on-failure"
    },
    "ShmSize": 67108864,
    "Sysctls": {
      "net.ipv4.ip_forward": "1"
    },
    "Ulimits": [
      {}
    ],
    "VolumeDriver": ""
  },
  "HostnamePath": "/var/lib/docker/containers/ba033ac4401106a3b513bc9d639eee123ad78ca3616b921167cd74b20e25ed39/hostname",
  "HostsPath": "/var/lib/docker/containers/ba033ac4401106a3b513bc9d639eee123ad78ca3616b921167cd74b20e25ed39/hosts",
  "Id": "ba033ac4401106a3b513bc9d639eee123ad78ca3616b921167cd74b20e25ed39",
  "Image": "04c5d3b7b0656168630d3ba35d8889bd0e9caafcaeb3004d2bfbc47e7c5d35d2",
  "LogPath": "/var/lib/docker/containers/1eb5fabf5a03807136561b3c00adcd2992b535d624d5e18b6cdc6a6844d9767b/1eb5fabf5a03807136561b3c00adcd2992b535d624d5e18b6cdc6a6844d9767b-json.log",
  "MountLabel": "",
  "Mounts": [
    {
      "Destination": "/data",
      "Driver": "local",
      "Mode": "ro,Z",
      "Name": "fac362...80535",
      "Propagation": "",
      "RW": false,
      "Source": "/data"
    }
  ],
  "Name": "/boring_euclid",
  "NetworkSettings": {
    "Bridge": "",
    "EndpointID": "",
    "Gateway": "",
    "GlobalIPv6Address": "",
    "GlobalIPv6PrefixLen": 0,
    "HairpinMode": false,
    "IPAddress": "",
    "IPPrefixLen": 0,
    "IPv6Gateway": "",
    "LinkLocalIPv6Address": "",
    "LinkLocalIPv6PrefixLen": 0,
    "MacAddress": "",
    "Networks": {
      "bridge": {
        "EndpointID": "7587b82f0dada3656fda26588aee72630c6fab1536d36e394b2bfbcf898c971d",
        "Gateway": "172.17.0.1",
        "GlobalIPv6Address": "",
        "GlobalIPv6PrefixLen": 0,
        "IPAddress": "172.17.0.2",
        "IPPrefixLen": 16,
        "IPv6Gateway": "",
        "MacAddress": "02:42:ac:12:00:02",
        "NetworkID": "7ea29fc1412292a2d7bba362f9253545fecdfa8ce9a6e37dd10ba8bee7129812"
      }
    },
    "SandboxID": "",
    "SandboxKey": ""
  },
  "Path": "/bin/sh",
  "ProcessLabel": "",
  "ResolvConfPath": "/var/lib/docker/containers/ba033ac4401106a3b513bc9d639eee123ad78ca3616b921167cd74b20e25ed39/resolv.conf",
  "RestartCount": 1,
  "State": {
    "Dead": false,
    "Error": "",
    "ExitCode": 9,
    "FinishedAt": "2015-01-06T15:47:32.080254511Z",
    "OOMKilled": false,
    "Paused": false,
    "Pid": 0,
    "Restarting": false,
    "Running": true,
    "StartedAt": "2015-01-06T15:47:32.072697474Z",
    "Status": "running"
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | no such container | [`ContainersJson404ErrorException`](../../doc/models/containers-json-404-error-exception.md) |
| 500 | server error | [`ContainersJson500ErrorException`](../../doc/models/containers-json-500-error-exception.md) |


# Container Kill

Send a POSIX signal to a container, defaulting to killing to the container.

```php
function containerKill(string $id, ?string $signal = 'SIGKILL'): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID or name of the container |
| `signal` | `?string` | Query, Optional | Signal to send to the container as an integer or string (e.g. `SIGINT`)<br><br>**Default**: `'SIGKILL'` |

## Response Type

**204**: no error

`void`

## Example Usage

```php
$id = 'id0';

$signal = 'SIGKILL';

$containerController = $client->getContainerController();

try {
    $containerController->containerKill(
        $id,
        $signal
    );
} catch (ContainersKill404ErrorException $exp) {
    echo 'Caught ContainersKill404ErrorException:', $exp;
} catch (ContainersKill500ErrorException $exp) {
    echo 'Caught ContainersKill500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | no such container | [`ContainersKill404ErrorException`](../../doc/models/containers-kill-404-error-exception.md) |
| 500 | server error | [`ContainersKill500ErrorException`](../../doc/models/containers-kill-500-error-exception.md) |


# Container Logs

Get `stdout` and `stderr` logs from a container.

Note: This endpoint works only for containers with the `json-file` or `journald` logging driver.

```php
function containerLogs(
    string $id,
    ?bool $follow = false,
    ?bool $stdout = false,
    ?bool $stderr = false,
    ?int $since = 0,
    ?bool $timestamps = false,
    ?string $tail = 'all'
): string
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID or name of the container |
| `follow` | `?bool` | Query, Optional | Return the logs as a stream.<br><br>This will return a `101` HTTP response with a `Connection: upgrade` header, then hijack the HTTP connection to send raw output. For more information about hijacking and the stream format, [see the documentation for the attach endpoint](#operation/ContainerAttach).<br><br>**Default**: `false` |
| `stdout` | `?bool` | Query, Optional | Return logs from `stdout`<br><br>**Default**: `false` |
| `stderr` | `?bool` | Query, Optional | Return logs from `stderr`<br><br>**Default**: `false` |
| `since` | `?int` | Query, Optional | Only return logs since this time, as a UNIX timestamp<br><br>**Default**: `0` |
| `timestamps` | `?bool` | Query, Optional | Add timestamps to every log line<br><br>**Default**: `false` |
| `tail` | `?string` | Query, Optional | Only return this number of log lines from the end of the logs. Specify as an integer or `all` to output all log lines.<br><br>**Default**: `'all'` |

## Response Type

**200**: logs returned as a string in response body

`string`

## Example Usage

```php
$id = 'id0';

$follow = false;

$stdout = false;

$stderr = false;

$since = 0;

$timestamps = false;

$tail = 'all';

$containerController = $client->getContainerController();

try {
    $result = $containerController->containerLogs(
        $id,
        $follow,
        $stdout,
        $stderr,
        $since,
        $timestamps,
        $tail
    );
    echo 'string:';
    var_dump($result);
} catch (ContainersLogs404ErrorException $exp) {
    echo 'Caught ContainersLogs404ErrorException:', $exp;
} catch (ContainersLogs500ErrorException $exp) {
    echo 'Caught ContainersLogs500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | no such container | [`ContainersLogs404ErrorException`](../../doc/models/containers-logs-404-error-exception.md) |
| 500 | server error | [`ContainersLogs500ErrorException`](../../doc/models/containers-logs-500-error-exception.md) |


# Container Pause

Use the cgroups freezer to suspend all processes in a container.

Traditionally, when suspending a process the `SIGSTOP` signal is used, which is observable by the process being suspended. With the cgroups freezer the process is unaware, and unable to capture, that it is being suspended, and subsequently resumed.

```php
function containerPause(string $id): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID or name of the container |

## Response Type

**204**: no error

`void`

## Example Usage

```php
$id = 'id0';

$containerController = $client->getContainerController();

try {
    $containerController->containerPause($id);
} catch (ContainersPause404ErrorException $exp) {
    echo 'Caught ContainersPause404ErrorException:', $exp;
} catch (ContainersPause500ErrorException $exp) {
    echo 'Caught ContainersPause500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | no such container | [`ContainersPause404ErrorException`](../../doc/models/containers-pause-404-error-exception.md) |
| 500 | server error | [`ContainersPause500ErrorException`](../../doc/models/containers-pause-500-error-exception.md) |


# Container Rename

```php
function containerRename(string $id, string $name): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID or name of the container |
| `name` | `string` | Query, Required | New name for the container |

## Response Type

**204**: no error

`void`

## Example Usage

```php
$id = 'id0';

$name = 'name0';

$containerController = $client->getContainerController();

try {
    $containerController->containerRename(
        $id,
        $name
    );
} catch (ContainersRename404ErrorException $exp) {
    echo 'Caught ContainersRename404ErrorException:', $exp;
} catch (ContainersRename409ErrorException $exp) {
    echo 'Caught ContainersRename409ErrorException:', $exp;
} catch (ContainersRename500ErrorException $exp) {
    echo 'Caught ContainersRename500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | no such container | [`ContainersRename404ErrorException`](../../doc/models/containers-rename-404-error-exception.md) |
| 409 | name already in use | [`ContainersRename409ErrorException`](../../doc/models/containers-rename-409-error-exception.md) |
| 500 | server error | [`ContainersRename500ErrorException`](../../doc/models/containers-rename-500-error-exception.md) |


# Container Resize

Resize the TTY for a container. You must restart the container for the resize to take effect.

```php
function containerResize(string $id, ?int $h = null, ?int $w = null): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID or name of the container |
| `h` | `?int` | Query, Optional | Height of the tty session in characters |
| `w` | `?int` | Query, Optional | Width of the tty session in characters |

## Response Type

**200**: no error

`void`

## Example Usage

```php
$id = 'id0';

$containerController = $client->getContainerController();

try {
    $containerController->containerResize($id);
} catch (ContainersResize404ErrorException $exp) {
    echo 'Caught ContainersResize404ErrorException:', $exp;
} catch (ContainersResize500ErrorException $exp) {
    echo 'Caught ContainersResize500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | no such container | [`ContainersResize404ErrorException`](../../doc/models/containers-resize-404-error-exception.md) |
| 500 | cannot resize container | [`ContainersResize500ErrorException`](../../doc/models/containers-resize-500-error-exception.md) |


# Container Restart

```php
function containerRestart(string $id, ?int $t = null): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID or name of the container |
| `t` | `?int` | Query, Optional | Number of seconds to wait before killing the container |

## Response Type

**204**: no error

`void`

## Example Usage

```php
$id = 'id0';

$containerController = $client->getContainerController();

try {
    $containerController->containerRestart($id);
} catch (ContainersRestart404ErrorException $exp) {
    echo 'Caught ContainersRestart404ErrorException:', $exp;
} catch (ContainersRestart500ErrorException $exp) {
    echo 'Caught ContainersRestart500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | no such container | [`ContainersRestart404ErrorException`](../../doc/models/containers-restart-404-error-exception.md) |
| 500 | server error | [`ContainersRestart500ErrorException`](../../doc/models/containers-restart-500-error-exception.md) |


# Container Start

```php
function containerStart(string $id, ?string $detachKeys = null): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID or name of the container |
| `detachKeys` | `?string` | Query, Optional | Override the key sequence for detaching a container. Format is a single character `[a-Z]` or `ctrl-<value>` where `<value>` is one of: `a-z`, `@`, `^`, `[`, `,` or `_`. |

## Response Type

**204**: no error

`void`

## Example Usage

```php
$id = 'id0';

$containerController = $client->getContainerController();

try {
    $containerController->containerStart($id);
} catch (ContainersStart404ErrorException $exp) {
    echo 'Caught ContainersStart404ErrorException:', $exp;
} catch (ContainersStart500ErrorException $exp) {
    echo 'Caught ContainersStart500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | no such container | [`ContainersStart404ErrorException`](../../doc/models/containers-start-404-error-exception.md) |
| 500 | server error | [`ContainersStart500ErrorException`](../../doc/models/containers-start-500-error-exception.md) |


# Container Stats

This endpoint returns a live stream of a container’s resource usage
statistics.

The `precpu_stats` is the CPU statistic of last read, which is used
for calculating the CPU usage percentage. It is not the same as the
`cpu_stats` field.

If either `precpu_stats.online_cpus` or `cpu_stats.online_cpus` is
nil then for compatibility with older daemons the length of the
corresponding `cpu_usage.percpu_usage` array should be used.

```php
function containerStats(string $id, ?bool $stream = true): array
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID or name of the container |
| `stream` | `?bool` | Query, Optional | Stream the output. If false, the stats will be output once and then it will disconnect.<br><br>**Default**: `true` |

## Response Type

**200**: no error

`array`

## Example Usage

```php
$id = 'id0';

$stream = true;

$containerController = $client->getContainerController();

try {
    $result = $containerController->containerStats(
        $id,
        $stream
    );
    echo 'array:';
    var_dump($result);
} catch (ContainersStats404ErrorException $exp) {
    echo 'Caught ContainersStats404ErrorException:', $exp;
} catch (ContainersStats500ErrorException $exp) {
    echo 'Caught ContainersStats500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response

```
{
  "blkio_stats": {},
  "cpu_stats": {
    "cpu_usage": {
      "percpu_usage": [
        8646879,
        24472255,
        36438778,
        30657443
      ],
      "total_usage": 100215355,
      "usage_in_kernelmode": 30000000,
      "usage_in_usermode": 50000000
    },
    "online_cpus": 4,
    "system_cpu_usage": 739306590000000,
    "throttling_data": {
      "periods": 0,
      "throttled_periods": 0,
      "throttled_time": 0
    }
  },
  "memory_stats": {
    "failcnt": 0,
    "limit": 67108864,
    "max_usage": 6651904,
    "stats": {
      "active_anon": 6537216,
      "active_file": 0,
      "cache": 0,
      "hierarchical_memory_limit": 67108864,
      "inactive_anon": 0,
      "inactive_file": 0,
      "mapped_file": 0,
      "pgfault": 964,
      "pgmajfault": 0,
      "pgpgin": 477,
      "pgpgout": 414,
      "rss": 6537216,
      "rss_huge": 6291456,
      "total_active_anon": 6537216,
      "total_active_file": 0,
      "total_cache": 0,
      "total_inactive_anon": 0,
      "total_inactive_file": 0,
      "total_mapped_file": 0,
      "total_pgfault": 964,
      "total_pgmajfault": 0,
      "total_pgpgin": 477,
      "total_pgpgout": 414,
      "total_rss": 6537216,
      "total_rss_huge": 6291456,
      "total_unevictable": 0,
      "total_writeback": 0,
      "unevictable": 0,
      "writeback": 0
    },
    "usage": 6537216
  },
  "networks": {
    "eth0": {
      "rx_bytes": 5338,
      "rx_dropped": 0,
      "rx_errors": 0,
      "rx_packets": 36,
      "tx_bytes": 648,
      "tx_dropped": 0,
      "tx_errors": 0,
      "tx_packets": 8
    },
    "eth5": {
      "rx_bytes": 4641,
      "rx_dropped": 0,
      "rx_errors": 0,
      "rx_packets": 26,
      "tx_bytes": 690,
      "tx_dropped": 0,
      "tx_errors": 0,
      "tx_packets": 9
    }
  },
  "pids_stats": {
    "current": 3
  },
  "precpu_stats": {
    "cpu_usage": {
      "percpu_usage": [
        8646879,
        24350896,
        36438778,
        30657443
      ],
      "total_usage": 100093996,
      "usage_in_kernelmode": 30000000,
      "usage_in_usermode": 50000000
    },
    "online_cpus": 4,
    "system_cpu_usage": 9492140000000,
    "throttling_data": {
      "periods": 0,
      "throttled_periods": 0,
      "throttled_time": 0
    }
  },
  "read": "2015-01-08T22:57:31.547920715Z"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | no such container | [`ContainersStats404ErrorException`](../../doc/models/containers-stats-404-error-exception.md) |
| 500 | server error | [`ContainersStats500ErrorException`](../../doc/models/containers-stats-500-error-exception.md) |


# Container Stop

```php
function containerStop(string $id, ?int $t = null): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID or name of the container |
| `t` | `?int` | Query, Optional | Number of seconds to wait before killing the container |

## Response Type

**204**: no error

`void`

## Example Usage

```php
$id = 'id0';

$containerController = $client->getContainerController();

try {
    $containerController->containerStop($id);
} catch (ContainersStop404ErrorException $exp) {
    echo 'Caught ContainersStop404ErrorException:', $exp;
} catch (ContainersStop500ErrorException $exp) {
    echo 'Caught ContainersStop500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | no such container | [`ContainersStop404ErrorException`](../../doc/models/containers-stop-404-error-exception.md) |
| 500 | server error | [`ContainersStop500ErrorException`](../../doc/models/containers-stop-500-error-exception.md) |


# Container Top

On Unix systems, this is done by running the `ps` command. This endpoint is not supported on Windows.

```php
function containerTop(string $id, ?string $psArgs = '-ef'): ContainersTopResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID or name of the container |
| `psArgs` | `?string` | Query, Optional | The arguments to pass to `ps`. For example, `aux`<br><br>**Default**: `'-ef'` |

## Response Type

**200**: no error

[`ContainersTopResponse`](../../doc/models/containers-top-response.md)

## Example Usage

```php
$id = 'id0';

$psArgs = '-ef';

$containerController = $client->getContainerController();

try {
    $result = $containerController->containerTop(
        $id,
        $psArgs
    );
    echo 'ContainersTopResponse:';
    var_dump($result);
} catch (ContainersTop404ErrorException $exp) {
    echo 'Caught ContainersTop404ErrorException:', $exp;
} catch (ContainersTop500ErrorException $exp) {
    echo 'Caught ContainersTop500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "Processes": [
    [
      "root",
      "13642",
      "882",
      "0",
      "17:03",
      "pts/0",
      "00:00:00",
      "/bin/bash"
    ],
    [
      "root",
      "13735",
      "13642",
      "0",
      "17:06",
      "pts/0",
      "00:00:00",
      "sleep 10"
    ]
  ],
  "Titles": [
    "UID",
    "PID",
    "PPID",
    "C",
    "STIME",
    "TTY",
    "TIME",
    "CMD"
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | no such container | [`ContainersTop404ErrorException`](../../doc/models/containers-top-404-error-exception.md) |
| 500 | server error | [`ContainersTop500ErrorException`](../../doc/models/containers-top-500-error-exception.md) |


# Container Unpause

Resume a container which has been paused.

```php
function containerUnpause(string $id): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID or name of the container |

## Response Type

**204**: no error

`void`

## Example Usage

```php
$id = 'id0';

$containerController = $client->getContainerController();

try {
    $containerController->containerUnpause($id);
} catch (ContainersUnpause404ErrorException $exp) {
    echo 'Caught ContainersUnpause404ErrorException:', $exp;
} catch (ContainersUnpause500ErrorException $exp) {
    echo 'Caught ContainersUnpause500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | no such container | [`ContainersUnpause404ErrorException`](../../doc/models/containers-unpause-404-error-exception.md) |
| 500 | server error | [`ContainersUnpause500ErrorException`](../../doc/models/containers-unpause-500-error-exception.md) |


# Container Update

Change various configuration options of a container without having to recreate it.

```php
function containerUpdate(string $id, ContainersUpdateRequest $body): ContainersUpdateResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID or name of the container |
| `body` | [`ContainersUpdateRequest`](../../doc/models/containers-update-request.md) | Body, Required | - |

## Response Type

**200**: The container has been updated.

[`ContainersUpdateResponse`](../../doc/models/containers-update-response.md)

## Example Usage

```php
$id = 'id0';

$body = ContainersUpdateRequestBuilder::init()
    ->blkioWeight(300)
    ->cpuPeriod(100000)
    ->cpuQuota(50000)
    ->cpuRealtimePeriod(1000000)
    ->cpuRealtimeRuntime(10000)
    ->cpuShares(512)
    ->cpusetCpus('0,1')
    ->cpusetMems('0')
    ->kernelMemory(52428800)
    ->memory(314572800)
    ->memoryReservation(209715200)
    ->memorySwap(514288000)
    ->restartPolicy(
        RestartPolicy3Builder::init()
            ->maximumRetryCount(4)
            ->name(NameEnum::ONFAILURE)
            ->build()
    )
    ->build();

$containerController = $client->getContainerController();

try {
    $result = $containerController->containerUpdate(
        $id,
        $body
    );
    echo 'ContainersUpdateResponse:';
    var_dump($result);
} catch (ContainersUpdate404ErrorException $exp) {
    echo 'Caught ContainersUpdate404ErrorException:', $exp;
} catch (ContainersUpdate500ErrorException $exp) {
    echo 'Caught ContainersUpdate500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | no such container | [`ContainersUpdate404ErrorException`](../../doc/models/containers-update-404-error-exception.md) |
| 500 | server error | [`ContainersUpdate500ErrorException`](../../doc/models/containers-update-500-error-exception.md) |


# Container Wait

Block until a container stops, then returns the exit code.

```php
function containerWait(string $id, ?string $condition = 'not-running'): ContainersWaitResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID or name of the container |
| `condition` | `?string` | Query, Optional | Wait until a container state reaches the given condition, either 'not-running' (default), 'next-exit', or 'removed'.<br><br>**Default**: `'not-running'` |

## Response Type

**200**: The container has exit.

[`ContainersWaitResponse`](../../doc/models/containers-wait-response.md)

## Example Usage

```php
$id = 'id0';

$condition = 'not-running';

$containerController = $client->getContainerController();

try {
    $result = $containerController->containerWait(
        $id,
        $condition
    );
    echo 'ContainersWaitResponse:';
    var_dump($result);
} catch (ContainersWait404ErrorException $exp) {
    echo 'Caught ContainersWait404ErrorException:', $exp;
} catch (ContainersWait500ErrorException $exp) {
    echo 'Caught ContainersWait500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | no such container | [`ContainersWait404ErrorException`](../../doc/models/containers-wait-404-error-exception.md) |
| 500 | server error | [`ContainersWait500ErrorException`](../../doc/models/containers-wait-500-error-exception.md) |

