# Authentication

Most Docker Hub API endpoints require you to authenticate using your
Docker credentials before using them.

Additionally, similar to the Docker Hub UI features, API endpoint responses may vary depending
on your plan (Free, Pro, or Team) and your account's permissions.

To learn more about the features available in each plan and to upgrade your existing plan, see [Docker Pricing](https://www.docker.com/pricing).

```php
$authenticationController = $client->getAuthenticationController();
```

## Class Name

`AuthenticationController`

## Methods

* [Post Users 2 FA Login](../../doc/controllers/authentication.md#post-users-2-fa-login)
* [Post Users Login](../../doc/controllers/authentication.md#post-users-login)


# Post Users 2 FA Login

When user has 2FA enabled, this is the second call to perform after
`/v2/users/login` call.

Creates and returns a bearer token in JWT format that you can use to authenticate with Docker Hub APIs.

The returned token is used in the HTTP Authorization header like `Authorization: Bearer {TOKEN}`.

Most Docker Hub APIs require this token either to consume or to get detailed information. For example, to list images in a private repository.

```php
function postUsers2FALogin(V2Users2faLoginRequest $body): V2Users2faLoginResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`V2Users2faLoginRequest`](../../doc/models/v2-users-2-fa-login-request.md) | Body, Required | Login details. |

## Response Type

**200**: Authentication successful

[`V2Users2faLoginResponse`](../../doc/models/v2-users-2-fa-login-response.md)

## Example Usage

```php
$body = V2Users2faLoginRequestBuilder::init(
    '123456',
    'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c'
)->build();

$authenticationController = $client->getAuthenticationController();

try {
    $result = $authenticationController->postUsers2FALogin($body);
    echo 'V2Users2faLoginResponse:';
    var_dump($result);
} catch (V2Users2faLogin401ErrorException $exp) {
    echo 'Caught V2Users2faLogin401ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Authentication failed or second factor required | [`V2Users2faLogin401ErrorException`](../../doc/models/v2-users-2-fa-login-401-error-exception.md) |


# Post Users Login

Creates and returns a bearer token in JWT format that you can use to
authenticate with Docker Hub APIs.

The returned token is used in the HTTP Authorization header like `Authorization: Bearer {TOKEN}`.

Most Docker Hub APIs require this token either to consume or to get detailed information. For example, to list images in a private repository.

```php
function postUsersLogin(V2UsersLoginRequest $body): V2UsersLoginResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`V2UsersLoginRequest`](../../doc/models/v2-users-login-request.md) | Body, Required | Login details. |

## Response Type

**200**: Authentication successful

[`V2UsersLoginResponse`](../../doc/models/v2-users-login-response.md)

## Example Usage

```php
$body = V2UsersLoginRequestBuilder::init(
    'hunter2',
    'myusername'
)->build();

$authenticationController = $client->getAuthenticationController();

try {
    $result = $authenticationController->postUsersLogin($body);
    echo 'V2UsersLoginResponse:';
    var_dump($result);
} catch (V2UsersLogin401ErrorException $exp) {
    echo 'Caught V2UsersLogin401ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Authentication failed or second factor required | [`V2UsersLogin401ErrorException`](../../doc/models/v2-users-login-401-error-exception.md) |

