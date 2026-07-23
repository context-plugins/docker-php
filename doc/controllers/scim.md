# Scim

SCIM is a provisioning system that lets you manage users within your identity provider (IdP).
For more information, see [System for Cross-domain Identity management](https://docs.docker.com/docker-hub/scim/).

```php
$scimController = $client->getScimController();
```

## Class Name

`ScimController`

## Methods

* [Listresourcetypes](../../doc/controllers/scim.md#listresourcetypes)
* [Getaresourcetype](../../doc/controllers/scim.md#getaresourcetype)
* [Listschemas](../../doc/controllers/scim.md#listschemas)
* [Getaschema](../../doc/controllers/scim.md#getaschema)
* [Getserviceproviderconfig](../../doc/controllers/scim.md#getserviceproviderconfig)
* [Listusers](../../doc/controllers/scim.md#listusers)
* [Createuser](../../doc/controllers/scim.md#createuser)
* [Getauser](../../doc/controllers/scim.md#getauser)
* [Updateauser](../../doc/controllers/scim.md#updateauser)


# Listresourcetypes

Returns all resource types supported for the SCIM configuration.

```php
function listresourcetypes(): ScimGetResourceTypesResp
```

## Response Type

**200**

[`ScimGetResourceTypesResp`](../../doc/models/scim-get-resource-types-resp.md)

## Example Usage

```php
$scimController = $client->getScimController();

try {
    $result = $scimController->listresourcetypes();
    echo 'ScimGetResourceTypesResp:';
    var_dump($result);
} catch (ScimErrorException $exp) {
    echo 'Caught ScimErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized | [`ScimErrorException`](../../doc/models/scim-error-exception.md) |
| 500 | Internal Error | [`ScimErrorException`](../../doc/models/scim-error-exception.md) |


# Getaresourcetype

Returns a resource type by name.

```php
function getaresourcetype(string $name): ScimResourceType
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Template, Required | - |

## Response Type

**200**

[`ScimResourceType`](../../doc/models/scim-resource-type.md)

## Example Usage

```php
$name = 'User';

$scimController = $client->getScimController();

try {
    $result = $scimController->getaresourcetype($name);
    echo 'ScimResourceType:';
    var_dump($result);
} catch (ScimErrorException $exp) {
    echo 'Caught ScimErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized | [`ScimErrorException`](../../doc/models/scim-error-exception.md) |
| 404 | Not Found | [`ScimErrorException`](../../doc/models/scim-error-exception.md) |
| 500 | Internal Error | [`ScimErrorException`](../../doc/models/scim-error-exception.md) |


# Listschemas

Returns all schemas supported for the SCIM configuration.

```php
function listschemas(): ScimGetSchemasResp
```

## Response Type

**200**

[`ScimGetSchemasResp`](../../doc/models/scim-get-schemas-resp.md)

## Example Usage

```php
$scimController = $client->getScimController();

try {
    $result = $scimController->listschemas();
    echo 'ScimGetSchemasResp:';
    var_dump($result);
} catch (ScimErrorException $exp) {
    echo 'Caught ScimErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized | [`ScimErrorException`](../../doc/models/scim-error-exception.md) |
| 500 | Internal Error | [`ScimErrorException`](../../doc/models/scim-error-exception.md) |


# Getaschema

Returns a schema by ID.

```php
function getaschema(string $id): ScimSchema
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | - |

## Response Type

**200**

[`ScimSchema`](../../doc/models/scim-schema.md)

## Example Usage

```php
$id = 'urn:ietf:params:scim:schemas:core:2.0:User';

$scimController = $client->getScimController();

try {
    $result = $scimController->getaschema($id);
    echo 'ScimSchema:';
    var_dump($result);
} catch (ScimErrorException $exp) {
    echo 'Caught ScimErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized | [`ScimErrorException`](../../doc/models/scim-error-exception.md) |
| 404 | Not Found | [`ScimErrorException`](../../doc/models/scim-error-exception.md) |
| 500 | Internal Error | [`ScimErrorException`](../../doc/models/scim-error-exception.md) |


# Getserviceproviderconfig

Returns a service provider config for Docker's configuration.

```php
function getserviceproviderconfig(): ScimServiceProviderConfig
```

## Response Type

**200**

[`ScimServiceProviderConfig`](../../doc/models/scim-service-provider-config.md)

## Example Usage

```php
$scimController = $client->getScimController();

try {
    $result = $scimController->getserviceproviderconfig();
    echo 'ScimServiceProviderConfig:';
    var_dump($result);
} catch (ScimErrorException $exp) {
    echo 'Caught ScimErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized | [`ScimErrorException`](../../doc/models/scim-error-exception.md) |
| 500 | Internal Error | [`ScimErrorException`](../../doc/models/scim-error-exception.md) |


# Listusers

List users, returns paginated users for an organization. Use `startIndex`
and `count` query parameters to receive paginated results.

**Sorting:**<br>
Sorting lets you to specify the order of returned resources by specifying
a combination of `sortBy` and `sortOrder` query parameters.

The `sortBy` parameter specifies the attribute whose value will be used
to order the returned responses. The `sortOrder` parameter defines the
order in which the `sortBy` parameter is applied. Allowed values are
"ascending" and "descending".

**Filtering:**<br>
You can request a subset of resources by specifying the `filter` query
parameter containing a filter expression. Attribute names and attribute
operators used in filters are case insensitive. The filter parameter
must contain at least one valid expression. Each expression must contain
an attribute name followed by an attribute operator and an optional
value.

Supported operators are listed below.

- `eq` equal
- `ne` not equal
- `co` contains
- `sw` starts with
- `and` Logical "and"
- `or` Logical "or"
- `not` "Not" function
- `()` Precedence grouping

```php
function listusers(
    ?int $startIndex = null,
    ?int $count = null,
    ?string $filter = null,
    ?string $attributes = null,
    ?string $sortOrder = null,
    ?string $sortBy = null
): ScimGetUsersResp
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `startIndex` | `?int` | Query, Optional | **Constraints**: `>= 1` |
| `count` | `?int` | Query, Optional | **Constraints**: `>= 1`, `<= 200` |
| `filter` | `?string` | Query, Optional | - |
| `attributes` | `?string` | Query, Optional | Comma delimited list of attributes to limit to in the response. |
| `sortOrder` | [`?string(SortOrderEnum)`](../../doc/models/sort-order-enum.md) | Query, Optional | - |
| `sortBy` | `?string` | Query, Optional | User attribute to sort by. |

## Response Type

**200**

[`ScimGetUsersResp`](../../doc/models/scim-get-users-resp.md)

## Example Usage

```php
$startIndex = 1;

$count = 10;

$filter = 'userName eq "jon.snow@docker.com"';

$attributes = 'userName,displayName';

$sortBy = 'userName';

$scimController = $client->getScimController();

try {
    $result = $scimController->listusers(
        $startIndex,
        $count,
        $filter,
        $attributes,
        null,
        $sortBy
    );
    echo 'ScimGetUsersResp:';
    var_dump($result);
} catch (ScimBadRequest1Exception $exp) {
    echo 'Caught ScimBadRequest1Exception:', $exp;
} catch (ScimErrorException $exp) {
    echo 'Caught ScimErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`ScimBadRequest1Exception`](../../doc/models/scim-bad-request-1-exception.md) |
| 401 | Unauthorized | [`ScimErrorException`](../../doc/models/scim-error-exception.md) |
| 403 | Forbidden | [`ScimErrorException`](../../doc/models/scim-error-exception.md) |
| 404 | Not Found | [`ScimErrorException`](../../doc/models/scim-error-exception.md) |
| 500 | Internal Error | [`ScimErrorException`](../../doc/models/scim-error-exception.md) |


# Createuser

Creates a user. If the user already exists by email, they are assigned
to the organization on the "company" team.

```php
function createuser(ScimCreateUserRequest $body): ScimUser
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`ScimCreateUserRequest`](../../doc/models/scim-create-user-request.md) | Body, Required | - |

## Response Type

**201**

[`ScimUser`](../../doc/models/scim-user.md)

## Example Usage

```php
$body = ScimCreateUserRequestBuilder::init(
    [
        'schemas1',
        'schemas2'
    ],
    'jon.snow@docker.com'
)->build();

$scimController = $client->getScimController();

try {
    $result = $scimController->createuser($body);
    echo 'ScimUser:';
    var_dump($result);
} catch (ScimBadRequest1Exception $exp) {
    echo 'Caught ScimBadRequest1Exception:', $exp;
} catch (ScimErrorException $exp) {
    echo 'Caught ScimErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`ScimBadRequest1Exception`](../../doc/models/scim-bad-request-1-exception.md) |
| 401 | Unauthorized | [`ScimErrorException`](../../doc/models/scim-error-exception.md) |
| 403 | Forbidden | [`ScimErrorException`](../../doc/models/scim-error-exception.md) |
| 404 | Not Found | [`ScimErrorException`](../../doc/models/scim-error-exception.md) |
| 409 | Conflict | [`ScimErrorException`](../../doc/models/scim-error-exception.md) |
| 500 | Internal Error | [`ScimErrorException`](../../doc/models/scim-error-exception.md) |


# Getauser

Returns a user by ID.

```php
function getauser(string $id): ScimUser
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The user ID. |

## Response Type

**200**

[`ScimUser`](../../doc/models/scim-user.md)

## Example Usage

```php
$id = 'd80f7c79-7730-49d8-9a41-7c42fb622d9c';

$scimController = $client->getScimController();

try {
    $result = $scimController->getauser($id);
    echo 'ScimUser:';
    var_dump($result);
} catch (ScimBadRequest1Exception $exp) {
    echo 'Caught ScimBadRequest1Exception:', $exp;
} catch (ScimErrorException $exp) {
    echo 'Caught ScimErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`ScimBadRequest1Exception`](../../doc/models/scim-bad-request-1-exception.md) |
| 401 | Unauthorized | [`ScimErrorException`](../../doc/models/scim-error-exception.md) |
| 403 | Forbidden | [`ScimErrorException`](../../doc/models/scim-error-exception.md) |
| 404 | Not Found | [`ScimErrorException`](../../doc/models/scim-error-exception.md) |
| 500 | Internal Error | [`ScimErrorException`](../../doc/models/scim-error-exception.md) |


# Updateauser

Updates a user. Use this route to change the user's name, activate,
and deactivate the user.

```php
function updateauser(string $id, ScimUpdateUserRequest $body): ScimUser
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The user ID. |
| `body` | [`ScimUpdateUserRequest`](../../doc/models/scim-update-user-request.md) | Body, Required | - |

## Response Type

**200**

[`ScimUser`](../../doc/models/scim-user.md)

## Example Usage

```php
$id = 'd80f7c79-7730-49d8-9a41-7c42fb622d9c';

$body = ScimUpdateUserRequestBuilder::init(
    [
        'schemas1',
        'schemas2'
    ]
)
    ->enabled(false)
    ->build();

$scimController = $client->getScimController();

try {
    $result = $scimController->updateauser(
        $id,
        $body
    );
    echo 'ScimUser:';
    var_dump($result);
} catch (ScimBadRequest1Exception $exp) {
    echo 'Caught ScimBadRequest1Exception:', $exp;
} catch (ScimErrorException $exp) {
    echo 'Caught ScimErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad Request | [`ScimBadRequest1Exception`](../../doc/models/scim-bad-request-1-exception.md) |
| 401 | Unauthorized | [`ScimErrorException`](../../doc/models/scim-error-exception.md) |
| 403 | Forbidden | [`ScimErrorException`](../../doc/models/scim-error-exception.md) |
| 404 | Not Found | [`ScimErrorException`](../../doc/models/scim-error-exception.md) |
| 409 | Conflict | [`ScimErrorException`](../../doc/models/scim-error-exception.md) |
| 500 | Internal Error | [`ScimErrorException`](../../doc/models/scim-error-exception.md) |

