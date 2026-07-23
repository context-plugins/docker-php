# System

```php
$systemController = $client->getSystemController();
```

## Class Name

`SystemController`

## Methods

* [System Ping](../../doc/controllers/system.md#system-ping)
* [System Auth](../../doc/controllers/system.md#system-auth)
* [System Events](../../doc/controllers/system.md#system-events)
* [System Info](../../doc/controllers/system.md#system-info)
* [System Data Usage](../../doc/controllers/system.md#system-data-usage)
* [System Version](../../doc/controllers/system.md#system-version)


# System Ping

This is a dummy endpoint you can use to test if the server is accessible.

```php
function systemPing(): string
```

## Response Type

**200**: no error

`string`

## Example Usage

```php
$systemController = $client->getSystemController();

try {
    $result = $systemController->systemPing();
    echo 'string:';
    var_dump($result);
} catch (Ping500ErrorException $exp) {
    echo 'Caught Ping500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | server error | [`Ping500ErrorException`](../../doc/models/ping-500-error-exception.md) |


# System Auth

Validate credentials for a registry and, if available, get an identity token for accessing the registry without password.

```php
function systemAuth(?AuthConfig $body = null): AuthResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?AuthConfig`](../../doc/models/auth-config.md) | Body, Optional | Authentication to check |

## Response Type

**200**: An identity token was generated successfully.

[`AuthResponse`](../../doc/models/auth-response.md)

## Example Usage

```php
$body = AuthConfigBuilder::init()
    ->password('xxxx')
    ->serveraddress('https://index.docker.io/v1/')
    ->username('hannibal')
    ->build();

$systemController = $client->getSystemController();

try {
    $result = $systemController->systemAuth($body);
    echo 'AuthResponse:';
    var_dump($result);
} catch (Auth500ErrorException $exp) {
    echo 'Caught Auth500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "IdentityToken": "9cbaf023786cd7...",
  "Status": "Login Succeeded"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | Server error | [`Auth500ErrorException`](../../doc/models/auth-500-error-exception.md) |


# System Events

Stream real-time events from the server.

Various objects within Docker report events when something happens to them.

Containers report these events: `attach`, `commit`, `copy`, `create`, `destroy`, `detach`, `die`, `exec_create`, `exec_detach`, `exec_start`, `export`, `health_status`, `kill`, `oom`, `pause`, `rename`, `resize`, `restart`, `start`, `stop`, `top`, `unpause`, and `update`

Images report these events: `delete`, `import`, `load`, `pull`, `push`, `save`, `tag`, and `untag`

Volumes report these events: `create`, `mount`, `unmount`, and `destroy`

Networks report these events: `create`, `connect`, `disconnect`, `destroy`, `update`, and `remove`

The Docker daemon reports these events: `reload`

Services report these events: `create`, `update`, and `remove`

Nodes report these events: `create`, `update`, and `remove`

Secrets report these events: `create`, `update`, and `remove`

Configs report these events: `create`, `update`, and `remove`

```php
function systemEvents(?string $since = null, ?string $until = null, ?string $filters = null): EventsResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `since` | `?string` | Query, Optional | Show events created since this timestamp then stream new events. |
| `until` | `?string` | Query, Optional | Show events created until this timestamp then stop streaming. |
| `filters` | `?string` | Query, Optional | A JSON encoded value of filters (a `map[string][]string`) to process on the event list. Available filters:<br><br>- `config=<string>` config name or ID<br>- `container=<string>` container name or ID<br>- `daemon=<string>` daemon name or ID<br>- `event=<string>` event type<br>- `image=<string>` image name or ID<br>- `label=<string>` image or container label<br>- `network=<string>` network name or ID<br>- `node=<string>` node ID<br>- `plugin`=<string> plugin name or ID<br>- `scope`＝<string> local or swarm<br>- `secret=<string>` secret name or ID<br>- `service=<string>` service name or ID<br>- `type=<string>` object to filter by, one of `container`, `image`, `volume`, `network`, `daemon`, `plugin`, `node`, `service`, `secret` or `config`<br>- `volume=<string>` volume name |

## Response Type

**200**: no error

[`EventsResponse`](../../doc/models/events-response.md)

## Example Usage

```php
$systemController = $client->getSystemController();

try {
    $result = $systemController->systemEvents();
    echo 'EventsResponse:';
    var_dump($result);
} catch (Events400ErrorException $exp) {
    echo 'Caught Events400ErrorException:', $exp;
} catch (Events500ErrorException $exp) {
    echo 'Caught Events500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "Action": "create",
  "Actor": {
    "Attributes": {
      "com.example.some-label": "some-label-value",
      "image": "alpine",
      "name": "my-container"
    },
    "ID": "ede54ee1afda366ab42f824e8a5ffd195155d853ceaec74a927f249ea270c743"
  },
  "Type": "container",
  "time": 1461943101
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | bad parameter | [`Events400ErrorException`](../../doc/models/events-400-error-exception.md) |
| 500 | server error | [`Events500ErrorException`](../../doc/models/events-500-error-exception.md) |


# System Info

```php
function systemInfo(): SystemInfo
```

## Response Type

**200**: No error

[`SystemInfo`](../../doc/models/system-info.md)

## Example Usage

```php
$systemController = $client->getSystemController();

try {
    $result = $systemController->systemInfo();
    echo 'SystemInfo:';
    var_dump($result);
} catch (Info500ErrorException $exp) {
    echo 'Caught Info500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | Server error | [`Info500ErrorException`](../../doc/models/info-500-error-exception.md) |


# System Data Usage

```php
function systemDataUsage(): SystemDfResponse
```

## Response Type

**200**: no error

[`SystemDfResponse`](../../doc/models/system-df-response.md)

## Example Usage

```php
$systemController = $client->getSystemController();

try {
    $result = $systemController->systemDataUsage();
    echo 'SystemDfResponse:';
    var_dump($result);
} catch (SystemDf500ErrorException $exp) {
    echo 'Caught SystemDf500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | server error | [`SystemDf500ErrorException`](../../doc/models/system-df-500-error-exception.md) |


# System Version

Returns the version of Docker that is running and various information about the system that Docker is running on.

```php
function systemVersion(): VersionResponse
```

## Response Type

**200**: no error

[`VersionResponse`](../../doc/models/version-response.md)

## Example Usage

```php
$systemController = $client->getSystemController();

try {
    $result = $systemController->systemVersion();
    echo 'VersionResponse:';
    var_dump($result);
} catch (Version500ErrorException $exp) {
    echo 'Caught Version500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "ApiVersion": "1.27",
  "Arch": "amd64",
  "BuildTime": "2016-06-14T07:09:13.444803460+00:00",
  "Experimental": true,
  "GitCommit": "deadbee",
  "GoVersion": "go1.7.5",
  "KernelVersion": "3.19.0-23-generic",
  "MinAPIVersion": "1.12",
  "Os": "linux",
  "Version": "17.04.0"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | server error | [`Version500ErrorException`](../../doc/models/version-500-error-exception.md) |

