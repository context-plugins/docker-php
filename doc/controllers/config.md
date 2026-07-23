# Config

Configs are application configurations that can be used by services. Swarm mode must be enabled for these endpoints to work.

```php
$configController = $client->getConfigController();
```

## Class Name

`ConfigController`

## Methods

* [Config List](../../doc/controllers/config.md#config-list)
* [Config Create](../../doc/controllers/config.md#config-create)
* [Config Delete](../../doc/controllers/config.md#config-delete)
* [Config Inspect](../../doc/controllers/config.md#config-inspect)
* [Config Update](../../doc/controllers/config.md#config-update)


# Config List

```php
function configList(?string $filters = null): array
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `filters` | `?string` | Query, Optional | A JSON encoded value of the filters (a `map[string][]string`) to process on the configs list. Available filters:<br><br>- `id=<config id>`<br>- `label=<key> or label=<key>=value`<br>- `name=<config name>`<br>- `names=<config name>` |

## Response Type

**200**: no error

[`Config[]`](../../doc/models/config.md)

## Example Usage

```php
$configController = $client->getConfigController();

try {
    $result = $configController->configList();
    echo 'Config[]:';
    var_dump($result);
} catch (Configs500ErrorException $exp) {
    echo 'Caught Configs500ErrorException:', $exp;
} catch (Configs503ErrorException $exp) {
    echo 'Caught Configs503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
[
  {
    "CreatedAt": "2016-11-05T01:20:17.327670065Z",
    "ID": "ktnbjxoalbkvbvedmg1urrz8h",
    "Spec": {
      "Name": "server.conf"
    },
    "UpdatedAt": "2016-11-05T01:20:17.327670065Z",
    "Version": {
      "Index": 11
    }
  }
]
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | server error | [`Configs500ErrorException`](../../doc/models/configs-500-error-exception.md) |
| 503 | node is not part of a swarm | [`Configs503ErrorException`](../../doc/models/configs-503-error-exception.md) |


# Config Create

```php
function configCreate(?ConfigSpec $body = null): ConfigsCreateResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?ConfigSpec`](../../doc/models/config-spec.md) | Body, Optional | - |

## Response Type

**201**: no error

[`ConfigsCreateResponse`](../../doc/models/configs-create-response.md)

## Example Usage

```php
$configController = $client->getConfigController();

try {
    $result = $configController->configCreate();
    echo 'ConfigsCreateResponse:';
    var_dump($result);
} catch (ConfigsCreate409ErrorException $exp) {
    echo 'Caught ConfigsCreate409ErrorException:', $exp;
} catch (ConfigsCreate500ErrorException $exp) {
    echo 'Caught ConfigsCreate500ErrorException:', $exp;
} catch (ConfigsCreate503ErrorException $exp) {
    echo 'Caught ConfigsCreate503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 409 | name conflicts with an existing object | [`ConfigsCreate409ErrorException`](../../doc/models/configs-create-409-error-exception.md) |
| 500 | server error | [`ConfigsCreate500ErrorException`](../../doc/models/configs-create-500-error-exception.md) |
| 503 | node is not part of a swarm | [`ConfigsCreate503ErrorException`](../../doc/models/configs-create-503-error-exception.md) |


# Config Delete

```php
function configDelete(string $id): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID of the config |

## Response Type

**204**: no error

`void`

## Example Usage

```php
$id = 'id0';

$configController = $client->getConfigController();

try {
    $configController->configDelete($id);
} catch (Configs404ErrorException $exp) {
    echo 'Caught Configs404ErrorException:', $exp;
} catch (Configs500ErrorException $exp) {
    echo 'Caught Configs500ErrorException:', $exp;
} catch (Configs503ErrorException $exp) {
    echo 'Caught Configs503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | config not found | [`Configs404ErrorException`](../../doc/models/configs-404-error-exception.md) |
| 500 | server error | [`Configs500ErrorException`](../../doc/models/configs-500-error-exception.md) |
| 503 | node is not part of a swarm | [`Configs503ErrorException`](../../doc/models/configs-503-error-exception.md) |


# Config Inspect

```php
function configInspect(string $id): Config
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID of the config |

## Response Type

**200**: no error

[`Config`](../../doc/models/config.md)

## Example Usage

```php
$id = 'id0';

$configController = $client->getConfigController();

try {
    $result = $configController->configInspect($id);
    echo 'Config:';
    var_dump($result);
} catch (Configs404ErrorException $exp) {
    echo 'Caught Configs404ErrorException:', $exp;
} catch (Configs500ErrorException $exp) {
    echo 'Caught Configs500ErrorException:', $exp;
} catch (Configs503ErrorException $exp) {
    echo 'Caught Configs503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "CreatedAt": "2016-11-05T01:20:17.327670065Z",
  "ID": "ktnbjxoalbkvbvedmg1urrz8h",
  "Spec": {
    "Name": "app-dev.crt"
  },
  "UpdatedAt": "2016-11-05T01:20:17.327670065Z",
  "Version": {
    "Index": 11
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | config not found | [`Configs404ErrorException`](../../doc/models/configs-404-error-exception.md) |
| 500 | server error | [`Configs500ErrorException`](../../doc/models/configs-500-error-exception.md) |
| 503 | node is not part of a swarm | [`Configs503ErrorException`](../../doc/models/configs-503-error-exception.md) |


# Config Update

```php
function configUpdate(string $id, int $version, ?ConfigSpec $body = null): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID or name of the config |
| `version` | `int` | Query, Required | The version number of the config object being updated. This is required to avoid conflicting writes. |
| `body` | [`?ConfigSpec`](../../doc/models/config-spec.md) | Body, Optional | The spec of the config to update. Currently, only the Labels field can be updated. All other fields must remain unchanged from the [ConfigInspect endpoint](#operation/ConfigInspect) response values. |

## Response Type

**200**: no error

`void`

## Example Usage

```php
$id = 'id0';

$version = 172;

$configController = $client->getConfigController();

try {
    $configController->configUpdate(
        $id,
        $version
    );
} catch (ConfigsUpdate400ErrorException $exp) {
    echo 'Caught ConfigsUpdate400ErrorException:', $exp;
} catch (ConfigsUpdate404ErrorException $exp) {
    echo 'Caught ConfigsUpdate404ErrorException:', $exp;
} catch (ConfigsUpdate500ErrorException $exp) {
    echo 'Caught ConfigsUpdate500ErrorException:', $exp;
} catch (ConfigsUpdate503ErrorException $exp) {
    echo 'Caught ConfigsUpdate503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | bad parameter | [`ConfigsUpdate400ErrorException`](../../doc/models/configs-update-400-error-exception.md) |
| 404 | no such config | [`ConfigsUpdate404ErrorException`](../../doc/models/configs-update-404-error-exception.md) |
| 500 | server error | [`ConfigsUpdate500ErrorException`](../../doc/models/configs-update-500-error-exception.md) |
| 503 | node is not part of a swarm | [`ConfigsUpdate503ErrorException`](../../doc/models/configs-update-503-error-exception.md) |

