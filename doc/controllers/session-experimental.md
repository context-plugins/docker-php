# Session Experimental

```php
$sessionExperimentalController = $client->getSessionExperimentalController();
```

## Class Name

`SessionExperimentalController`


# Session

Start a new interactive session with a server. Session allows server to call back to the client for advanced capabilities.

> **Note**: This endpoint is *experimental* and only available if the daemon is started with experimental
> features enabled. The specifications for this endpoint may still change in a future version of the API.

### Hijacking

This endpoint hijacks the HTTP connection to HTTP2 transport that allows the client to expose gPRC services on that connection.

For example, the client sends this request to upgrade the connection:

```
POST /session HTTP/1.1
Upgrade: h2c
Connection: Upgrade
```

The Docker daemon will respond with a `101 UPGRADED` response follow with the raw stream:

```
HTTP/1.1 101 UPGRADED
Connection: Upgrade
Upgrade: h2c
```

```php
function session(): void
```

## Response Type

**200**

`void`

## Example Usage

```php
$sessionExperimentalController = $client->getSessionExperimentalController();

try {
    $sessionExperimentalController->session();
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | bad parameter | `ApiException` |
| 500 | server error | `ApiException` |

