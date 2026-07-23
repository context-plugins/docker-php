# Service

Services are the definitions of tasks to run on a swarm. Swarm mode must be enabled for these endpoints to work.

```php
$serviceController = $client->getServiceController();
```

## Class Name

`ServiceController`

## Methods

* [Service List](../../doc/controllers/service.md#service-list)
* [Service Create](../../doc/controllers/service.md#service-create)
* [Service Delete](../../doc/controllers/service.md#service-delete)
* [Service Inspect](../../doc/controllers/service.md#service-inspect)
* [Service Logs](../../doc/controllers/service.md#service-logs)
* [Service Update](../../doc/controllers/service.md#service-update)


# Service List

```php
function serviceList(?string $filters = null): array
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `filters` | `?string` | Query, Optional | A JSON encoded value of the filters (a `map[string][]string`) to process on the services list. Available filters:<br><br>- `id=<service id>`<br>- `label=<service label>`<br>- `mode=["replicated"\|"global"]`<br>- `name=<service name>` |

## Response Type

**200**: no error

[`Service[]`](../../doc/models/service.md)

## Example Usage

```php
$serviceController = $client->getServiceController();

try {
    $result = $serviceController->serviceList();
    echo 'Service[]:';
    var_dump($result);
} catch (Services500ErrorException $exp) {
    echo 'Caught Services500ErrorException:', $exp;
} catch (Services503ErrorException $exp) {
    echo 'Caught Services503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | server error | [`Services500ErrorException`](../../doc/models/services-500-error-exception.md) |
| 503 | node is not part of a swarm | [`Services503ErrorException`](../../doc/models/services-503-error-exception.md) |


# Service Create

```php
function serviceCreate(ServicesCreateRequest $body, ?string $xRegistryAuth = null): ServicesCreateResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`ServicesCreateRequest`](../../doc/models/services-create-request.md) | Body, Required | - |
| `xRegistryAuth` | `?string` | Header, Optional | A base64-encoded auth configuration for pulling from private registries. [See the authentication section for details.](#section/Authentication) |

## Response Type

**201**: no error

[`ServicesCreateResponse`](../../doc/models/services-create-response.md)

## Example Usage

```php
$body = ServicesCreateRequestBuilder::init()->build();

$serviceController = $client->getServiceController();

try {
    $result = $serviceController->serviceCreate($body);
    echo 'ServicesCreateResponse:';
    var_dump($result);
} catch (ServicesCreate400ErrorException $exp) {
    echo 'Caught ServicesCreate400ErrorException:', $exp;
} catch (ServicesCreate403ErrorException $exp) {
    echo 'Caught ServicesCreate403ErrorException:', $exp;
} catch (ServicesCreate409ErrorException $exp) {
    echo 'Caught ServicesCreate409ErrorException:', $exp;
} catch (ServicesCreate500ErrorException $exp) {
    echo 'Caught ServicesCreate500ErrorException:', $exp;
} catch (ServicesCreate503ErrorException $exp) {
    echo 'Caught ServicesCreate503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | bad parameter | [`ServicesCreate400ErrorException`](../../doc/models/services-create-400-error-exception.md) |
| 403 | network is not eligible for services | [`ServicesCreate403ErrorException`](../../doc/models/services-create-403-error-exception.md) |
| 409 | name conflicts with an existing service | [`ServicesCreate409ErrorException`](../../doc/models/services-create-409-error-exception.md) |
| 500 | server error | [`ServicesCreate500ErrorException`](../../doc/models/services-create-500-error-exception.md) |
| 503 | node is not part of a swarm | [`ServicesCreate503ErrorException`](../../doc/models/services-create-503-error-exception.md) |


# Service Delete

```php
function serviceDelete(string $id): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID or name of service. |

## Response Type

**200**: no error

`void`

## Example Usage

```php
$id = 'id0';

$serviceController = $client->getServiceController();

try {
    $serviceController->serviceDelete($id);
} catch (Services404ErrorException $exp) {
    echo 'Caught Services404ErrorException:', $exp;
} catch (Services500ErrorException $exp) {
    echo 'Caught Services500ErrorException:', $exp;
} catch (Services503ErrorException $exp) {
    echo 'Caught Services503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | no such service | [`Services404ErrorException`](../../doc/models/services-404-error-exception.md) |
| 500 | server error | [`Services500ErrorException`](../../doc/models/services-500-error-exception.md) |
| 503 | node is not part of a swarm | [`Services503ErrorException`](../../doc/models/services-503-error-exception.md) |


# Service Inspect

```php
function serviceInspect(string $id, ?bool $insertDefaults = false): Service
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID or name of service. |
| `insertDefaults` | `?bool` | Query, Optional | Fill empty fields with default values.<br><br>**Default**: `false` |

## Response Type

**200**: no error

[`Service`](../../doc/models/service.md)

## Example Usage

```php
$id = 'id0';

$insertDefaults = false;

$serviceController = $client->getServiceController();

try {
    $result = $serviceController->serviceInspect(
        $id,
        $insertDefaults
    );
    echo 'Service:';
    var_dump($result);
} catch (Services404ErrorException $exp) {
    echo 'Caught Services404ErrorException:', $exp;
} catch (Services500ErrorException $exp) {
    echo 'Caught Services500ErrorException:', $exp;
} catch (Services503ErrorException $exp) {
    echo 'Caught Services503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | no such service | [`Services404ErrorException`](../../doc/models/services-404-error-exception.md) |
| 500 | server error | [`Services500ErrorException`](../../doc/models/services-500-error-exception.md) |
| 503 | node is not part of a swarm | [`Services503ErrorException`](../../doc/models/services-503-error-exception.md) |


# Service Logs

Get `stdout` and `stderr` logs from a service.

**Note**: This endpoint works only for services with the `json-file` or `journald` logging drivers.

```php
function serviceLogs(
    string $id,
    ?bool $details = false,
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
| `id` | `string` | Template, Required | ID or name of the service |
| `details` | `?bool` | Query, Optional | Show service context and extra details provided to logs.<br><br>**Default**: `false` |
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

$details = false;

$follow = false;

$stdout = false;

$stderr = false;

$since = 0;

$timestamps = false;

$tail = 'all';

$serviceController = $client->getServiceController();

try {
    $result = $serviceController->serviceLogs(
        $id,
        $details,
        $follow,
        $stdout,
        $stderr,
        $since,
        $timestamps,
        $tail
    );
    echo 'string:';
    var_dump($result);
} catch (ServicesLogs404ErrorException $exp) {
    echo 'Caught ServicesLogs404ErrorException:', $exp;
} catch (ServicesLogs500ErrorException $exp) {
    echo 'Caught ServicesLogs500ErrorException:', $exp;
} catch (ServicesLogs503ErrorException $exp) {
    echo 'Caught ServicesLogs503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | no such service | [`ServicesLogs404ErrorException`](../../doc/models/services-logs-404-error-exception.md) |
| 500 | server error | [`ServicesLogs500ErrorException`](../../doc/models/services-logs-500-error-exception.md) |
| 503 | node is not part of a swarm | [`ServicesLogs503ErrorException`](../../doc/models/services-logs-503-error-exception.md) |


# Service Update

```php
function serviceUpdate(
    string $id,
    int $version,
    ServicesUpdateRequest $body,
    ?string $registryAuthFrom = 'spec',
    ?string $rollback = null,
    ?string $xRegistryAuth = null
): ServiceUpdateResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID or name of service. |
| `version` | `int` | Query, Required | The version number of the service object being updated. This is required to avoid conflicting writes. |
| `body` | [`ServicesUpdateRequest`](../../doc/models/services-update-request.md) | Body, Required | - |
| `registryAuthFrom` | `?string` | Query, Optional | If the X-Registry-Auth header is not specified, this parameter indicates where to find registry authorization credentials. The valid values are `spec` and `previous-spec`.<br><br>**Default**: `'spec'` |
| `rollback` | `?string` | Query, Optional | Set to this parameter to `previous` to cause a server-side rollback to the previous service spec. The supplied spec will be ignored in this case. |
| `xRegistryAuth` | `?string` | Header, Optional | A base64-encoded auth configuration for pulling from private registries. [See the authentication section for details.](#section/Authentication) |

## Response Type

**200**: no error

[`ServiceUpdateResponse`](../../doc/models/service-update-response.md)

## Example Usage

```php
$id = 'id0';

$version = 172;

$body = ServicesUpdateRequestBuilder::init()->build();

$registryAuthFrom = 'spec';

$serviceController = $client->getServiceController();

try {
    $result = $serviceController->serviceUpdate(
        $id,
        $version,
        $body,
        $registryAuthFrom
    );
    echo 'ServiceUpdateResponse:';
    var_dump($result);
} catch (ServicesUpdate400ErrorException $exp) {
    echo 'Caught ServicesUpdate400ErrorException:', $exp;
} catch (ServicesUpdate404ErrorException $exp) {
    echo 'Caught ServicesUpdate404ErrorException:', $exp;
} catch (ServicesUpdate500ErrorException $exp) {
    echo 'Caught ServicesUpdate500ErrorException:', $exp;
} catch (ServicesUpdate503ErrorException $exp) {
    echo 'Caught ServicesUpdate503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | bad parameter | [`ServicesUpdate400ErrorException`](../../doc/models/services-update-400-error-exception.md) |
| 404 | no such service | [`ServicesUpdate404ErrorException`](../../doc/models/services-update-404-error-exception.md) |
| 500 | server error | [`ServicesUpdate500ErrorException`](../../doc/models/services-update-500-error-exception.md) |
| 503 | node is not part of a swarm | [`ServicesUpdate503ErrorException`](../../doc/models/services-update-503-error-exception.md) |

