# Exec

Run new commands inside running containers. See the [command-line reference](https://docs.docker.com/engine/reference/commandline/exec/) for more information.

To exec a command in a container, you first need to create an exec instance, then start it. These two API endpoints are wrapped up in a single command-line command, `docker exec`.

```php
$execController = $client->getExecController();
```

## Class Name

`ExecController`

## Methods

* [Container Exec](../../doc/controllers/exec.md#container-exec)
* [Exec Inspect](../../doc/controllers/exec.md#exec-inspect)
* [Exec Resize](../../doc/controllers/exec.md#exec-resize)
* [Exec Start](../../doc/controllers/exec.md#exec-start)


# Container Exec

Run a command inside a running container.

```php
function containerExec(string $id, ContainersExecRequest $body): ContainersExecResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID or name of container |
| `body` | [`ContainersExecRequest`](../../doc/models/containers-exec-request.md) | Body, Required | Exec configuration |

## Response Type

**201**: no error

[`ContainersExecResponse`](../../doc/models/containers-exec-response.md)

## Example Usage

```php
$id = 'id0';

$body = ContainersExecRequestBuilder::init()
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

$execController = $client->getExecController();

try {
    $result = $execController->containerExec(
        $id,
        $body
    );
    echo 'ContainersExecResponse:';
    var_dump($result);
} catch (ContainersExec404ErrorException $exp) {
    echo 'Caught ContainersExec404ErrorException:', $exp;
} catch (ContainersExec409ErrorException $exp) {
    echo 'Caught ContainersExec409ErrorException:', $exp;
} catch (ContainersExec500ErrorException $exp) {
    echo 'Caught ContainersExec500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | no such container | [`ContainersExec404ErrorException`](../../doc/models/containers-exec-404-error-exception.md) |
| 409 | container is paused | [`ContainersExec409ErrorException`](../../doc/models/containers-exec-409-error-exception.md) |
| 500 | Server error | [`ContainersExec500ErrorException`](../../doc/models/containers-exec-500-error-exception.md) |


# Exec Inspect

Return low-level information about an exec instance.

```php
function execInspect(string $id): ExecJsonResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | Exec instance ID |

## Response Type

**200**: No error

[`ExecJsonResponse`](../../doc/models/exec-json-response.md)

## Example Usage

```php
$id = 'id0';

$execController = $client->getExecController();

try {
    $result = $execController->execInspect($id);
    echo 'ExecJsonResponse:';
    var_dump($result);
} catch (ExecJson404ErrorException $exp) {
    echo 'Caught ExecJson404ErrorException:', $exp;
} catch (ExecJson500ErrorException $exp) {
    echo 'Caught ExecJson500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "CanRemove": false,
  "ContainerID": "b53ee82b53a40c7dca428523e34f741f3abc51d9f297a14ff874bf761b995126",
  "DetachKeys": "",
  "ExitCode": 2,
  "ID": "f33bbfb39f5b142420f4759b2348913bd4a8d1a6d7fd56499cb41a1bb91d7b3b",
  "OpenStderr": true,
  "OpenStdin": true,
  "OpenStdout": true,
  "Pid": 42000,
  "ProcessConfig": {
    "arguments": [
      "-c",
      "exit 2"
    ],
    "entrypoint": "sh",
    "privileged": false,
    "tty": true,
    "user": "1000"
  },
  "Running": false
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | No such exec instance | [`ExecJson404ErrorException`](../../doc/models/exec-json-404-error-exception.md) |
| 500 | Server error | [`ExecJson500ErrorException`](../../doc/models/exec-json-500-error-exception.md) |


# Exec Resize

Resize the TTY session used by an exec instance. This endpoint only works if `tty` was specified as part of creating and starting the exec instance.

```php
function execResize(string $id, ?int $h = null, ?int $w = null): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | Exec instance ID |
| `h` | `?int` | Query, Optional | Height of the TTY session in characters |
| `w` | `?int` | Query, Optional | Width of the TTY session in characters |

## Response Type

**201**: No error

`void`

## Example Usage

```php
$id = 'id0';

$execController = $client->getExecController();

try {
    $execController->execResize($id);
} catch (ExecResize404ErrorException $exp) {
    echo 'Caught ExecResize404ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | No such exec instance | [`ExecResize404ErrorException`](../../doc/models/exec-resize-404-error-exception.md) |


# Exec Start

Starts a previously set up exec instance. If detach is true, this endpoint returns immediately after starting the command. Otherwise, it sets up an interactive session with the command.

```php
function execStart(string $id, ?ExecStartRequest $body = null): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | Exec instance ID |
| `body` | [`?ExecStartRequest`](../../doc/models/exec-start-request.md) | Body, Optional | - |

## Response Type

**200**: No error

`void`

## Example Usage

```php
$id = 'id0';

$body = ExecStartRequestBuilder::init()
    ->detach(false)
    ->tty(false)
    ->build();

$execController = $client->getExecController();

try {
    $execController->execStart(
        $id,
        $body
    );
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | No such exec instance | `ApiException` |
| 409 | Container is stopped or paused | `ApiException` |

