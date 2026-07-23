# Plugin

```php
$pluginController = $client->getPluginController();
```

## Class Name

`PluginController`

## Methods

* [Plugin List](../../doc/controllers/plugin.md#plugin-list)
* [Plugin Create](../../doc/controllers/plugin.md#plugin-create)
* [Get Plugin Privileges](../../doc/controllers/plugin.md#get-plugin-privileges)
* [Plugin Pull](../../doc/controllers/plugin.md#plugin-pull)
* [Plugin Delete](../../doc/controllers/plugin.md#plugin-delete)
* [Plugin Disable](../../doc/controllers/plugin.md#plugin-disable)
* [Plugin Enable](../../doc/controllers/plugin.md#plugin-enable)
* [Plugin Inspect](../../doc/controllers/plugin.md#plugin-inspect)
* [Plugin Push](../../doc/controllers/plugin.md#plugin-push)
* [Plugin Set](../../doc/controllers/plugin.md#plugin-set)
* [Plugin Upgrade](../../doc/controllers/plugin.md#plugin-upgrade)


# Plugin List

Returns information about installed plugins.

```php
function pluginList(?string $filters = null): array
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `filters` | `?string` | Query, Optional | A JSON encoded value of the filters (a `map[string][]string`) to process on the plugin list. Available filters:<br><br>- `capability=<capability name>`<br>- `enable=<true>\|<false>` |

## Response Type

**200**: No error

[`Plugin[]`](../../doc/models/plugin.md)

## Example Usage

```php
$pluginController = $client->getPluginController();

try {
    $result = $pluginController->pluginList();
    echo 'Plugin[]:';
    var_dump($result);
} catch (Plugins500ErrorException $exp) {
    echo 'Caught Plugins500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | Server error | [`Plugins500ErrorException`](../../doc/models/plugins-500-error-exception.md) |


# Plugin Create

```php
function pluginCreate(string $name, ?array $body = null): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Query, Required | The name of the plugin. The `:latest` tag is optional, and is the default if omitted. |
| `body` | `?array` | Body, Optional | Path to tar containing plugin rootfs and manifest |

## Response Type

**204**: no error

`void`

## Example Usage

```php
$name = 'name0';

$pluginController = $client->getPluginController();

try {
    $pluginController->pluginCreate($name);
} catch (PluginsCreate500ErrorException $exp) {
    echo 'Caught PluginsCreate500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | server error | [`PluginsCreate500ErrorException`](../../doc/models/plugins-create-500-error-exception.md) |


# Get Plugin Privileges

```php
function getPluginPrivileges(string $remote): array
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `remote` | `string` | Query, Required | The name of the plugin. The `:latest` tag is optional, and is the default if omitted. |

## Response Type

**200**: no error

[`PluginsPrivilegesResponse[]`](../../doc/models/plugins-privileges-response.md)

## Example Usage

```php
$remote = 'remote6';

$pluginController = $client->getPluginController();

try {
    $result = $pluginController->getPluginPrivileges($remote);
    echo 'PluginsPrivilegesResponse[]:';
    var_dump($result);
} catch (PluginsPrivileges500ErrorException $exp) {
    echo 'Caught PluginsPrivileges500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
[
  {
    "Description": "",
    "Name": "network",
    "Value": [
      "host"
    ]
  },
  {
    "Description": "",
    "Name": "mount",
    "Value": [
      "/data"
    ]
  },
  {
    "Description": "",
    "Name": "device",
    "Value": [
      "/dev/cpu_dma_latency"
    ]
  }
]
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | server error | [`PluginsPrivileges500ErrorException`](../../doc/models/plugins-privileges-500-error-exception.md) |


# Plugin Pull

Pulls and installs a plugin. After the plugin is installed, it can be enabled using the [`POST /plugins/{name}/enable` endpoint](#operation/PostPluginsEnable).

```php
function pluginPull(
    string $remote,
    ?string $name = null,
    ?string $xRegistryAuth = null,
    ?array $body = null
): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `remote` | `string` | Query, Required | Remote reference for plugin to install.<br><br>The `:latest` tag is optional, and is used as the default if omitted. |
| `name` | `?string` | Query, Optional | Local name for the pulled plugin.<br><br>The `:latest` tag is optional, and is used as the default if omitted. |
| `xRegistryAuth` | `?string` | Header, Optional | A base64-encoded auth configuration to use when pulling a plugin from a registry. [See the authentication section for details.](#section/Authentication) |
| `body` | [`?(PluginPullBody[])`](../../doc/models/plugin-pull-body.md) | Body, Optional | - |

## Response Type

**204**: no error

`void`

## Example Usage

```php
$remote = 'remote6';

$body = [
    PluginPullBodyBuilder::init()->build()
];

$pluginController = $client->getPluginController();

try {
    $pluginController->pluginPull(
        $remote,
        null,
        null,
        $body
    );
} catch (PluginsPull500ErrorException $exp) {
    echo 'Caught PluginsPull500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | server error | [`PluginsPull500ErrorException`](../../doc/models/plugins-pull-500-error-exception.md) |


# Plugin Delete

```php
function pluginDelete(string $name, ?bool $force = false): PluginsResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Template, Required | The name of the plugin. The `:latest` tag is optional, and is the default if omitted. |
| `force` | `?bool` | Query, Optional | Disable the plugin before removing. This may result in issues if the plugin is in use by a container.<br><br>**Default**: `false` |

## Response Type

**200**: no error

[`PluginsResponse`](../../doc/models/plugins-response.md)

## Example Usage

```php
$name = 'name0';

$force = false;

$pluginController = $client->getPluginController();

try {
    $result = $pluginController->pluginDelete(
        $name,
        $force
    );
    echo 'PluginsResponse:';
    var_dump($result);
} catch (Plugins404ErrorException $exp) {
    echo 'Caught Plugins404ErrorException:', $exp;
} catch (Plugins500ErrorException $exp) {
    echo 'Caught Plugins500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | plugin is not installed | [`Plugins404ErrorException`](../../doc/models/plugins-404-error-exception.md) |
| 500 | server error | [`Plugins500ErrorException`](../../doc/models/plugins-500-error-exception.md) |


# Plugin Disable

```php
function pluginDisable(string $name): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Template, Required | The name of the plugin. The `:latest` tag is optional, and is the default if omitted. |

## Response Type

**200**: no error

`void`

## Example Usage

```php
$name = 'name0';

$pluginController = $client->getPluginController();

try {
    $pluginController->pluginDisable($name);
} catch (PluginsDisable404ErrorException $exp) {
    echo 'Caught PluginsDisable404ErrorException:', $exp;
} catch (PluginsDisable500ErrorException $exp) {
    echo 'Caught PluginsDisable500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | plugin is not installed | [`PluginsDisable404ErrorException`](../../doc/models/plugins-disable-404-error-exception.md) |
| 500 | server error | [`PluginsDisable500ErrorException`](../../doc/models/plugins-disable-500-error-exception.md) |


# Plugin Enable

```php
function pluginEnable(string $name, ?int $timeout = 0): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Template, Required | The name of the plugin. The `:latest` tag is optional, and is the default if omitted. |
| `timeout` | `?int` | Query, Optional | Set the HTTP client timeout (in seconds)<br><br>**Default**: `0` |

## Response Type

**200**: no error

`void`

## Example Usage

```php
$name = 'name0';

$timeout = 0;

$pluginController = $client->getPluginController();

try {
    $pluginController->pluginEnable(
        $name,
        $timeout
    );
} catch (PluginsEnable404ErrorException $exp) {
    echo 'Caught PluginsEnable404ErrorException:', $exp;
} catch (PluginsEnable500ErrorException $exp) {
    echo 'Caught PluginsEnable500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | plugin is not installed | [`PluginsEnable404ErrorException`](../../doc/models/plugins-enable-404-error-exception.md) |
| 500 | server error | [`PluginsEnable500ErrorException`](../../doc/models/plugins-enable-500-error-exception.md) |


# Plugin Inspect

```php
function pluginInspect(string $name): PluginsJsonResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Template, Required | The name of the plugin. The `:latest` tag is optional, and is the default if omitted. |

## Response Type

**200**: no error

[`PluginsJsonResponse`](../../doc/models/plugins-json-response.md)

## Example Usage

```php
$name = 'name0';

$pluginController = $client->getPluginController();

try {
    $result = $pluginController->pluginInspect($name);
    echo 'PluginsJsonResponse:';
    var_dump($result);
} catch (PluginsJson404ErrorException $exp) {
    echo 'Caught PluginsJson404ErrorException:', $exp;
} catch (PluginsJson500ErrorException $exp) {
    echo 'Caught PluginsJson500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | plugin is not installed | [`PluginsJson404ErrorException`](../../doc/models/plugins-json-404-error-exception.md) |
| 500 | server error | [`PluginsJson500ErrorException`](../../doc/models/plugins-json-500-error-exception.md) |


# Plugin Push

Push a plugin to the registry.

```php
function pluginPush(string $name): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Template, Required | The name of the plugin. The `:latest` tag is optional, and is the default if omitted. |

## Response Type

**200**: no error

`void`

## Example Usage

```php
$name = 'name0';

$pluginController = $client->getPluginController();

try {
    $pluginController->pluginPush($name);
} catch (PluginsPush404ErrorException $exp) {
    echo 'Caught PluginsPush404ErrorException:', $exp;
} catch (PluginsPush500ErrorException $exp) {
    echo 'Caught PluginsPush500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | plugin not installed | [`PluginsPush404ErrorException`](../../doc/models/plugins-push-404-error-exception.md) |
| 500 | server error | [`PluginsPush500ErrorException`](../../doc/models/plugins-push-500-error-exception.md) |


# Plugin Set

```php
function pluginSet(string $name, ?array $body = null): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Template, Required | The name of the plugin. The `:latest` tag is optional, and is the default if omitted. |
| `body` | `?(string[])` | Body, Optional | - |

## Response Type

**204**: No error

`void`

## Example Usage

```php
$name = 'name0';

$pluginController = $client->getPluginController();

try {
    $pluginController->pluginSet($name);
} catch (PluginsSet404ErrorException $exp) {
    echo 'Caught PluginsSet404ErrorException:', $exp;
} catch (PluginsSet500ErrorException $exp) {
    echo 'Caught PluginsSet500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | Plugin not installed | [`PluginsSet404ErrorException`](../../doc/models/plugins-set-404-error-exception.md) |
| 500 | Server error | [`PluginsSet500ErrorException`](../../doc/models/plugins-set-500-error-exception.md) |


# Plugin Upgrade

```php
function pluginUpgrade(string $name, string $remote, ?string $xRegistryAuth = null, ?array $body = null): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Template, Required | The name of the plugin. The `:latest` tag is optional, and is the default if omitted. |
| `remote` | `string` | Query, Required | Remote reference to upgrade to.<br><br>The `:latest` tag is optional, and is used as the default if omitted. |
| `xRegistryAuth` | `?string` | Header, Optional | A base64-encoded auth configuration to use when pulling a plugin from a registry. [See the authentication section for details.](#section/Authentication) |
| `body` | [`?(PluginPullBody[])`](../../doc/models/plugin-pull-body.md) | Body, Optional | - |

## Response Type

**204**: no error

`void`

## Example Usage

```php
$name = 'name0';

$remote = 'remote6';

$body = [
    PluginPullBodyBuilder::init()->build()
];

$pluginController = $client->getPluginController();

try {
    $pluginController->pluginUpgrade(
        $name,
        $remote,
        null,
        $body
    );
} catch (PluginsUpgrade404ErrorException $exp) {
    echo 'Caught PluginsUpgrade404ErrorException:', $exp;
} catch (PluginsUpgrade500ErrorException $exp) {
    echo 'Caught PluginsUpgrade500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | plugin not installed | [`PluginsUpgrade404ErrorException`](../../doc/models/plugins-upgrade-404-error-exception.md) |
| 500 | server error | [`PluginsUpgrade500ErrorException`](../../doc/models/plugins-upgrade-500-error-exception.md) |

