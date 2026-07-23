# Network

Networks are user-defined networks that containers can be attached to. See the [networking documentation](https://docs.docker.com/engine/userguide/networking/) for more information.

```php
$networkController = $client->getNetworkController();
```

## Class Name

`NetworkController`

## Methods

* [Network List](../../doc/controllers/network.md#network-list)
* [Network Create](../../doc/controllers/network.md#network-create)
* [Network Prune](../../doc/controllers/network.md#network-prune)
* [Network Delete](../../doc/controllers/network.md#network-delete)
* [Network Inspect](../../doc/controllers/network.md#network-inspect)
* [Network Connect](../../doc/controllers/network.md#network-connect)
* [Network Disconnect](../../doc/controllers/network.md#network-disconnect)


# Network List

Returns a list of networks. For details on the format, see [the network inspect endpoint](#operation/NetworkInspect).

Note that it uses a different, smaller representation of a network than inspecting a single network. For example,
the list of containers attached to the network is not propagated in API versions 1.28 and up.

```php
function networkList(?string $filters = null): array
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `filters` | `?string` | Query, Optional | JSON encoded value of the filters (a `map[string][]string`) to process on the networks list. Available filters:<br><br>- `driver=<driver-name>` Matches a network's driver.<br>- `id=<network-id>` Matches all or part of a network ID.<br>- `label=<key>` or `label=<key>=<value>` of a network label.<br>- `name=<network-name>` Matches all or part of a network name.<br>- `scope=["swarm"\|"global"\|"local"]` Filters networks by scope (`swarm`, `global`, or `local`).<br>- `type=["custom"\|"builtin"]` Filters networks by type. The `custom` keyword returns all user-defined networks. |

## Response Type

**200**: No error

[`Network[]`](../../doc/models/network.md)

## Example Usage

```php
$networkController = $client->getNetworkController();

try {
    $result = $networkController->networkList();
    echo 'Network[]:';
    var_dump($result);
} catch (Networks500ErrorException $exp) {
    echo 'Caught Networks500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | Server error | [`Networks500ErrorException`](../../doc/models/networks-500-error-exception.md) |


# Network Create

```php
function networkCreate(NetworksCreateRequest $body): NetworksCreateResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`NetworksCreateRequest`](../../doc/models/networks-create-request.md) | Body, Required | Network configuration |

## Response Type

**201**: No error

[`NetworksCreateResponse`](../../doc/models/networks-create-response.md)

## Example Usage

```php
$body = NetworksCreateRequestBuilder::init(
    'Name6'
)
    ->driver('bridge')
    ->build();

$networkController = $client->getNetworkController();

try {
    $result = $networkController->networkCreate($body);
    echo 'NetworksCreateResponse:';
    var_dump($result);
} catch (NetworksCreate403ErrorException $exp) {
    echo 'Caught NetworksCreate403ErrorException:', $exp;
} catch (NetworksCreate404ErrorException $exp) {
    echo 'Caught NetworksCreate404ErrorException:', $exp;
} catch (NetworksCreate500ErrorException $exp) {
    echo 'Caught NetworksCreate500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 403 | operation not supported for pre-defined networks | [`NetworksCreate403ErrorException`](../../doc/models/networks-create-403-error-exception.md) |
| 404 | plugin not found | [`NetworksCreate404ErrorException`](../../doc/models/networks-create-404-error-exception.md) |
| 500 | Server error | [`NetworksCreate500ErrorException`](../../doc/models/networks-create-500-error-exception.md) |


# Network Prune

```php
function networkPrune(?string $filters = null): NetworksPruneResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `filters` | `?string` | Query, Optional | Filters to process on the prune list, encoded as JSON (a `map[string][]string`).<br><br>Available filters:<br><br>- `until=<timestamp>` Prune networks created before this timestamp. The `<timestamp>` can be Unix timestamps, date formatted timestamps, or Go duration strings (e.g. `10m`, `1h30m`) computed relative to the daemon machine’s time.<br>- `label` (`label=<key>`, `label=<key>=<value>`, `label!=<key>`, or `label!=<key>=<value>`) Prune networks with (or without, in case `label!=...` is used) the specified labels. |

## Response Type

**200**: No error

[`NetworksPruneResponse`](../../doc/models/networks-prune-response.md)

## Example Usage

```php
$networkController = $client->getNetworkController();

try {
    $result = $networkController->networkPrune();
    echo 'NetworksPruneResponse:';
    var_dump($result);
} catch (NetworksPrune500ErrorException $exp) {
    echo 'Caught NetworksPrune500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | Server error | [`NetworksPrune500ErrorException`](../../doc/models/networks-prune-500-error-exception.md) |


# Network Delete

```php
function networkDelete(string $id): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | Network ID or name |

## Response Type

**204**: No error

`void`

## Example Usage

```php
$id = 'id0';

$networkController = $client->getNetworkController();

try {
    $networkController->networkDelete($id);
} catch (Networks403ErrorException $exp) {
    echo 'Caught Networks403ErrorException:', $exp;
} catch (Networks404ErrorException $exp) {
    echo 'Caught Networks404ErrorException:', $exp;
} catch (Networks500ErrorException $exp) {
    echo 'Caught Networks500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 403 | operation not supported for pre-defined networks | [`Networks403ErrorException`](../../doc/models/networks-403-error-exception.md) |
| 404 | no such network | [`Networks404ErrorException`](../../doc/models/networks-404-error-exception.md) |
| 500 | Server error | [`Networks500ErrorException`](../../doc/models/networks-500-error-exception.md) |


# Network Inspect

```php
function networkInspect(string $id, ?bool $verbose = false, ?string $scope = null): Network
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | Network ID or name |
| `verbose` | `?bool` | Query, Optional | Detailed inspect output for troubleshooting<br><br>**Default**: `false` |
| `scope` | `?string` | Query, Optional | Filter the network by scope (swarm, global, or local) |

## Response Type

**200**: No error

[`Network`](../../doc/models/network.md)

## Example Usage

```php
$id = 'id0';

$verbose = false;

$networkController = $client->getNetworkController();

try {
    $result = $networkController->networkInspect(
        $id,
        $verbose
    );
    echo 'Network:';
    var_dump($result);
} catch (Networks404ErrorException $exp) {
    echo 'Caught Networks404ErrorException:', $exp;
} catch (Networks500ErrorException $exp) {
    echo 'Caught Networks500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | Network not found | [`Networks404ErrorException`](../../doc/models/networks-404-error-exception.md) |
| 500 | Server error | [`Networks500ErrorException`](../../doc/models/networks-500-error-exception.md) |


# Network Connect

```php
function networkConnect(string $id, string $contentType, FileWrapper $body): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | Network ID or name |
| `contentType` | [`string(ContentType1Enum)`](../../doc/models/content-type-1-enum.md) | Header, Required | - |
| `body` | [`FileWrapper`](../../doc/models/file.md) | Form, Required | - |

## Response Type

**200**: No error

`void`

## Example Usage

```php
$id = 'id0';

$contentType = ContentType1Enum::ENUM_APPLICATIONOCTETSTREAM;

$body = FileWrapper::createFromPath('dummy_file');

$networkController = $client->getNetworkController();

try {
    $networkController->networkConnect(
        $id,
        $contentType,
        $body
    );
} catch (NetworksConnect403ErrorException $exp) {
    echo 'Caught NetworksConnect403ErrorException:', $exp;
} catch (NetworksConnect404ErrorException $exp) {
    echo 'Caught NetworksConnect404ErrorException:', $exp;
} catch (NetworksConnect500ErrorException $exp) {
    echo 'Caught NetworksConnect500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 403 | Operation not supported for swarm scoped networks | [`NetworksConnect403ErrorException`](../../doc/models/networks-connect-403-error-exception.md) |
| 404 | Network or container not found | [`NetworksConnect404ErrorException`](../../doc/models/networks-connect-404-error-exception.md) |
| 500 | Server error | [`NetworksConnect500ErrorException`](../../doc/models/networks-connect-500-error-exception.md) |


# Network Disconnect

```php
function networkDisconnect(string $id, NetworksDisconnectRequest $body): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | Network ID or name |
| `body` | [`NetworksDisconnectRequest`](../../doc/models/networks-disconnect-request.md) | Body, Required | - |

## Response Type

**200**: No error

`void`

## Example Usage

```php
$id = 'id0';

$body = NetworksDisconnectRequestBuilder::init()->build();

$networkController = $client->getNetworkController();

try {
    $networkController->networkDisconnect(
        $id,
        $body
    );
} catch (NetworksDisconnect403ErrorException $exp) {
    echo 'Caught NetworksDisconnect403ErrorException:', $exp;
} catch (NetworksDisconnect404ErrorException $exp) {
    echo 'Caught NetworksDisconnect404ErrorException:', $exp;
} catch (NetworksDisconnect500ErrorException $exp) {
    echo 'Caught NetworksDisconnect500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 403 | Operation not supported for swarm scoped networks | [`NetworksDisconnect403ErrorException`](../../doc/models/networks-disconnect-403-error-exception.md) |
| 404 | Network or container not found | [`NetworksDisconnect404ErrorException`](../../doc/models/networks-disconnect-404-error-exception.md) |
| 500 | Server error | [`NetworksDisconnect500ErrorException`](../../doc/models/networks-disconnect-500-error-exception.md) |

