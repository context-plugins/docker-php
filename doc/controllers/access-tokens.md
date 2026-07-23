# Access-Tokens

The Personal Access Token endpoints lets you manage personal access tokens. For more
information, see [Access Tokens](https://docs.docker.com/docker-hub/access-tokens/).

You can use a personal access token instead of a password in the [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/)
or in the [Create an authentication token](#operation/PostUsersLogin) route to obtain a bearer
token.

### Scopes

For each scope grouping (in this case "repo"), you only need to define 1 scope as any lower
scopes are assumed. For example: If you define `repo:write`, the API assumes the scope of both
`repo:read` *and* `repo:public_read` as well. If you were to define both `repo:write` *and*
`repo:read`, then `repo:read` is assumed by `repo:write` and ignored.

***Treat your personal access token like your password and keep it secret. You cannot retrieve
your token after it is generated.***

```php
$accessTokensController = $client->getAccessTokensController();
```

## Class Name

`AccessTokensController`

## Methods

* [Getalistofpersonalaccesstokens](../../doc/controllers/access-tokens.md#getalistofpersonalaccesstokens)
* [Createapersonalaccesstoken](../../doc/controllers/access-tokens.md#createapersonalaccesstoken)
* [Deleteapersonalaccesstoken](../../doc/controllers/access-tokens.md#deleteapersonalaccesstoken)
* [Getapersonalaccesstoken](../../doc/controllers/access-tokens.md#getapersonalaccesstoken)
* [Updateapersonalaccesstoken](../../doc/controllers/access-tokens.md#updateapersonalaccesstoken)


# Getalistofpersonalaccesstokens

Returns a paginated list of personal access tokens.

```php
function getalistofpersonalaccesstokens(?float $page = 1, ?float $pageSize = 10): GetAccessTokensResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `page` | `?float` | Query, Optional | **Default**: `1` |
| `pageSize` | `?float` | Query, Optional | **Default**: `10` |

## Response Type

**200**: OK

[`GetAccessTokensResponse`](../../doc/models/get-access-tokens-response.md)

## Example Usage

```php
$page = 1;

$pageSize = 10;

$accessTokensController = $client->getAccessTokensController();

try {
    $result = $accessTokensController->getalistofpersonalaccesstokens(
        $page,
        $pageSize
    );
    echo 'GetAccessTokensResponse:';
    var_dump($result);
} catch (V2AccessTokens400ErrorException $exp) {
    echo 'Caught V2AccessTokens400ErrorException:', $exp;
} catch (ErrorException $exp) {
    echo 'Caught ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`V2AccessTokens400ErrorException`](../../doc/models/v2-access-tokens-400-error-exception.md) |
| 401 | Unauthorized | [`ErrorException`](../../doc/models/error-exception.md) |


# Createapersonalaccesstoken

Creates and returns a personal access token.

```php
function createapersonalaccesstoken(CreateAccessTokenRequest $body): CreateAccessTokensResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`CreateAccessTokenRequest`](../../doc/models/create-access-token-request.md) | Body, Required | - |

## Response Type

**201**: Created

[`CreateAccessTokensResponse`](../../doc/models/create-access-tokens-response.md)

## Example Usage

```php
$body = CreateAccessTokenRequestBuilder::init(
    [
        'repo:read'
    ],
    'My read only token'
)->build();

$accessTokensController = $client->getAccessTokensController();

try {
    $result = $accessTokensController->createapersonalaccesstoken($body);
    echo 'CreateAccessTokensResponse:';
    var_dump($result);
} catch (V2AccessTokens400ErrorException $exp) {
    echo 'Caught V2AccessTokens400ErrorException:', $exp;
} catch (ErrorException $exp) {
    echo 'Caught ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`V2AccessTokens400ErrorException`](../../doc/models/v2-access-tokens-400-error-exception.md) |
| 401 | Unauthorized | [`ErrorException`](../../doc/models/error-exception.md) |


# Deleteapersonalaccesstoken

Deletes a personal access token permanently. This cannot be undone.

```php
function deleteapersonalaccesstoken(string $uuid): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `uuid` | `string` | Template, Required | - |

## Response Type

**204**: A successful response.

`void`

## Example Usage

```php
$uuid = 'uuid6';

$accessTokensController = $client->getAccessTokensController();

try {
    $accessTokensController->deleteapersonalaccesstoken($uuid);
} catch (ErrorException $exp) {
    echo 'Caught ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized | [`ErrorException`](../../doc/models/error-exception.md) |
| 404 | Not Found | [`ErrorException`](../../doc/models/error-exception.md) |


# Getapersonalaccesstoken

Returns a personal access token by UUID.

```php
function getapersonalaccesstoken(string $uuid): AccessToken
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `uuid` | `string` | Template, Required | - |

## Response Type

**200**: OK

[`AccessToken`](../../doc/models/access-token.md)

## Example Usage

```php
$uuid = 'uuid6';

$accessTokensController = $client->getAccessTokensController();

try {
    $result = $accessTokensController->getapersonalaccesstoken($uuid);
    echo 'AccessToken:';
    var_dump($result);
} catch (ErrorException $exp) {
    echo 'Caught ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized | [`ErrorException`](../../doc/models/error-exception.md) |
| 404 | Not Found | [`ErrorException`](../../doc/models/error-exception.md) |


# Updateapersonalaccesstoken

Updates a personal access token partially. You can either update the
token's label or enable/disable it.

```php
function updateapersonalaccesstoken(string $uuid, PatchAccessTokenRequest $body): PatchAccessTokenResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `uuid` | `string` | Template, Required | - |
| `body` | [`PatchAccessTokenRequest`](../../doc/models/patch-access-token-request.md) | Body, Required | - |

## Response Type

**200**: OK

[`PatchAccessTokenResponse`](../../doc/models/patch-access-token-response.md)

## Example Usage

```php
$uuid = 'uuid6';

$body = PatchAccessTokenRequestBuilder::init()
    ->isActive(false)
    ->tokenLabel('My read only token')
    ->build();

$accessTokensController = $client->getAccessTokensController();

try {
    $result = $accessTokensController->updateapersonalaccesstoken(
        $uuid,
        $body
    );
    echo 'PatchAccessTokenResponse:';
    var_dump($result);
} catch (V2AccessTokens400ErrorException $exp) {
    echo 'Caught V2AccessTokens400ErrorException:', $exp;
} catch (ErrorException $exp) {
    echo 'Caught ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`V2AccessTokens400ErrorException`](../../doc/models/v2-access-tokens-400-error-exception.md) |
| 401 | Unauthorized | [`ErrorException`](../../doc/models/error-exception.md) |

