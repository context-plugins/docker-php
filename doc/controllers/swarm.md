# Swarm

Engines can be clustered together in a swarm. See [the swarm mode documentation](https://docs.docker.com/engine/swarm/) for more information.

```php
$swarmController = $client->getSwarmController();
```

## Class Name

`SwarmController`

## Methods

* [Swarm Inspect](../../doc/controllers/swarm.md#swarm-inspect)
* [Swarm Init](../../doc/controllers/swarm.md#swarm-init)
* [Swarm Join](../../doc/controllers/swarm.md#swarm-join)
* [Swarm Leave](../../doc/controllers/swarm.md#swarm-leave)
* [Swarm Unlock](../../doc/controllers/swarm.md#swarm-unlock)
* [Swarm Unlockkey](../../doc/controllers/swarm.md#swarm-unlockkey)
* [Swarm Update](../../doc/controllers/swarm.md#swarm-update)


# Swarm Inspect

```php
function swarmInspect()
```

## Response Type

**200**: no error

`mixed`

## Example Usage

```php
$swarmController = $client->getSwarmController();

try {
    $result = $swarmController->swarmInspect();
    echo 'mixed:';
    var_dump($result);
} catch (Swarm404ErrorException $exp) {
    echo 'Caught Swarm404ErrorException:', $exp;
} catch (Swarm500ErrorException $exp) {
    echo 'Caught Swarm500ErrorException:', $exp;
} catch (Swarm503ErrorException $exp) {
    echo 'Caught Swarm503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | no such swarm | [`Swarm404ErrorException`](../../doc/models/swarm-404-error-exception.md) |
| 500 | server error | [`Swarm500ErrorException`](../../doc/models/swarm-500-error-exception.md) |
| 503 | node is not part of a swarm | [`Swarm503ErrorException`](../../doc/models/swarm-503-error-exception.md) |


# Swarm Init

```php
function swarmInit(SwarmInitRequest $body): string
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`SwarmInitRequest`](../../doc/models/swarm-init-request.md) | Body, Required | - |

## Response Type

**200**: no error

`string`

## Example Usage

```php
$body = SwarmInitRequestBuilder::init()
    ->advertiseAddr('192.168.1.1:2377')
    ->forceNewCluster(false)
    ->listenAddr('0.0.0.0:2377')
    ->spec(
        SpecBuilder::init()
            ->cAConfig(ApiHelper::deserialize('{}'))
            ->dispatcher(ApiHelper::deserialize('{}'))
            ->encryptionConfig(
                EncryptionConfig2Builder::init()
                    ->autoLockManagers(false)
                    ->build()
            )
            ->orchestration(ApiHelper::deserialize('{}'))
            ->raft(
                Raft2Builder::init()->build()
            )->build()
    )->build();

$swarmController = $client->getSwarmController();

try {
    $result = $swarmController->swarmInit($body);
    echo 'string:';
    var_dump($result);
} catch (SwarmInit400ErrorException $exp) {
    echo 'Caught SwarmInit400ErrorException:', $exp;
} catch (SwarmInit500ErrorException $exp) {
    echo 'Caught SwarmInit500ErrorException:', $exp;
} catch (SwarmInit503ErrorException $exp) {
    echo 'Caught SwarmInit503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response

```
"7v2t30z9blmxuhnyo6s4cpenp"
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | bad parameter | [`SwarmInit400ErrorException`](../../doc/models/swarm-init-400-error-exception.md) |
| 500 | server error | [`SwarmInit500ErrorException`](../../doc/models/swarm-init-500-error-exception.md) |
| 503 | node is already part of a swarm | [`SwarmInit503ErrorException`](../../doc/models/swarm-init-503-error-exception.md) |


# Swarm Join

```php
function swarmJoin(SwarmJoinRequest $body): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`SwarmJoinRequest`](../../doc/models/swarm-join-request.md) | Body, Required | - |

## Response Type

**200**: no error

`void`

## Example Usage

```php
$body = SwarmJoinRequestBuilder::init()
    ->advertiseAddr('192.168.1.1:2377')
    ->joinToken('SWMTKN-1-3pu6hszjas19xyp7ghgosyx9k8atbfcr8p2is99znpy26u2lkl-7p73s1dx5in4tatdymyhg9hu2')
    ->listenAddr('0.0.0.0:2377')
    ->remoteAddrs('["node1:2377"]')
    ->build();

$swarmController = $client->getSwarmController();

try {
    $swarmController->swarmJoin($body);
} catch (SwarmJoin400ErrorException $exp) {
    echo 'Caught SwarmJoin400ErrorException:', $exp;
} catch (SwarmJoin500ErrorException $exp) {
    echo 'Caught SwarmJoin500ErrorException:', $exp;
} catch (SwarmJoin503ErrorException $exp) {
    echo 'Caught SwarmJoin503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | bad parameter | [`SwarmJoin400ErrorException`](../../doc/models/swarm-join-400-error-exception.md) |
| 500 | server error | [`SwarmJoin500ErrorException`](../../doc/models/swarm-join-500-error-exception.md) |
| 503 | node is already part of a swarm | [`SwarmJoin503ErrorException`](../../doc/models/swarm-join-503-error-exception.md) |


# Swarm Leave

```php
function swarmLeave(?bool $force = false): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `force` | `?bool` | Query, Optional | Force leave swarm, even if this is the last manager or that it will break the cluster.<br><br>**Default**: `false` |

## Response Type

**200**: no error

`void`

## Example Usage

```php
$force = false;

$swarmController = $client->getSwarmController();

try {
    $swarmController->swarmLeave($force);
} catch (SwarmLeave500ErrorException $exp) {
    echo 'Caught SwarmLeave500ErrorException:', $exp;
} catch (SwarmLeave503ErrorException $exp) {
    echo 'Caught SwarmLeave503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | server error | [`SwarmLeave500ErrorException`](../../doc/models/swarm-leave-500-error-exception.md) |
| 503 | node is not part of a swarm | [`SwarmLeave503ErrorException`](../../doc/models/swarm-leave-503-error-exception.md) |


# Swarm Unlock

```php
function swarmUnlock(SwarmUnlockRequest $body): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`SwarmUnlockRequest`](../../doc/models/swarm-unlock-request.md) | Body, Required | - |

## Response Type

**200**: no error

`void`

## Example Usage

```php
$body = SwarmUnlockRequestBuilder::init()
    ->unlockKey('SWMKEY-1-7c37Cc8654o6p38HnroywCi19pllOnGtbdZEgtKxZu8')
    ->build();

$swarmController = $client->getSwarmController();

try {
    $swarmController->swarmUnlock($body);
} catch (SwarmUnlock500ErrorException $exp) {
    echo 'Caught SwarmUnlock500ErrorException:', $exp;
} catch (SwarmUnlock503ErrorException $exp) {
    echo 'Caught SwarmUnlock503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | server error | [`SwarmUnlock500ErrorException`](../../doc/models/swarm-unlock-500-error-exception.md) |
| 503 | node is not part of a swarm | [`SwarmUnlock503ErrorException`](../../doc/models/swarm-unlock-503-error-exception.md) |


# Swarm Unlockkey

```php
function swarmUnlockkey(): SwarmUnlockkeyResponse
```

## Response Type

**200**: no error

[`SwarmUnlockkeyResponse`](../../doc/models/swarm-unlockkey-response.md)

## Example Usage

```php
$swarmController = $client->getSwarmController();

try {
    $result = $swarmController->swarmUnlockkey();
    echo 'SwarmUnlockkeyResponse:';
    var_dump($result);
} catch (SwarmUnlockkey500ErrorException $exp) {
    echo 'Caught SwarmUnlockkey500ErrorException:', $exp;
} catch (SwarmUnlockkey503ErrorException $exp) {
    echo 'Caught SwarmUnlockkey503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | server error | [`SwarmUnlockkey500ErrorException`](../../doc/models/swarm-unlockkey-500-error-exception.md) |
| 503 | node is not part of a swarm | [`SwarmUnlockkey503ErrorException`](../../doc/models/swarm-unlockkey-503-error-exception.md) |


# Swarm Update

```php
function swarmUpdate(
    int $version,
    SwarmSpec $body,
    ?bool $rotateWorkerToken = false,
    ?bool $rotateManagerToken = false,
    ?bool $rotateManagerUnlockKey = false
): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `version` | `int` | Query, Required | The version number of the swarm object being updated. This is required to avoid conflicting writes. |
| `body` | [`SwarmSpec`](../../doc/models/swarm-spec.md) | Body, Required | - |
| `rotateWorkerToken` | `?bool` | Query, Optional | Rotate the worker join token.<br><br>**Default**: `false` |
| `rotateManagerToken` | `?bool` | Query, Optional | Rotate the manager join token.<br><br>**Default**: `false` |
| `rotateManagerUnlockKey` | `?bool` | Query, Optional | Rotate the manager unlock key.<br><br>**Default**: `false` |

## Response Type

**200**: no error

`void`

## Example Usage

```php
$version = 172;

$body = SwarmSpecBuilder::init()
    ->labels(
        [
            'com.example.corp.department' => 'engineering',
            'com.example.corp.type' => 'production'
        ]
    )
    ->name('default')
    ->build();

$rotateWorkerToken = false;

$rotateManagerToken = false;

$rotateManagerUnlockKey = false;

$swarmController = $client->getSwarmController();

try {
    $swarmController->swarmUpdate(
        $version,
        $body,
        $rotateWorkerToken,
        $rotateManagerToken,
        $rotateManagerUnlockKey
    );
} catch (SwarmUpdate400ErrorException $exp) {
    echo 'Caught SwarmUpdate400ErrorException:', $exp;
} catch (SwarmUpdate500ErrorException $exp) {
    echo 'Caught SwarmUpdate500ErrorException:', $exp;
} catch (SwarmUpdate503ErrorException $exp) {
    echo 'Caught SwarmUpdate503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | bad parameter | [`SwarmUpdate400ErrorException`](../../doc/models/swarm-update-400-error-exception.md) |
| 500 | server error | [`SwarmUpdate500ErrorException`](../../doc/models/swarm-update-500-error-exception.md) |
| 503 | node is not part of a swarm | [`SwarmUpdate503ErrorException`](../../doc/models/swarm-update-503-error-exception.md) |

