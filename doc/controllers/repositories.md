# Repositories

The repository endpoints allow you to manage your repository's
configuration like description.

```php
$repositoriesController = $client->getRepositoriesController();
```

## Class Name

`RepositoriesController`

## Methods

* [Listrepositorytags](../../doc/controllers/repositories.md#listrepositorytags)
* [Readrepositorytag](../../doc/controllers/repositories.md#readrepositorytag)


# Listrepositorytags

```php
function listrepositorytags(
    string $mNamespace,
    string $repository,
    ?int $page = null,
    ?int $pageSize = null
): PaginatedTags
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `mNamespace` | `string` | Template, Required | - |
| `repository` | `string` | Template, Required | - |
| `page` | `?int` | Query, Optional | Page number to get. Defaults to 1. |
| `pageSize` | `?int` | Query, Optional | Number of items to get per page. Defaults to 10. Max of 100. |

## Response Type

**200**: list repository tags

[`PaginatedTags`](../../doc/models/paginated-tags.md)

## Example Usage

```php
$namespace = 'namespace2';

$repository = 'repository0';

$repositoriesController = $client->getRepositoriesController();

try {
    $result = $repositoriesController->listrepositorytags(
        $namespace,
        $repository
    );
    echo 'PaginatedTags:';
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
| 403 | Forbidden | [`ErrorException`](../../doc/models/error-exception.md) |
| 404 | Not Found | [`ErrorException`](../../doc/models/error-exception.md) |


# Readrepositorytag

```php
function readrepositorytag(string $mNamespace, string $repository, string $tag): Tag
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `mNamespace` | `string` | Template, Required | - |
| `repository` | `string` | Template, Required | - |
| `tag` | `string` | Template, Required | - |

## Response Type

**200**: repository tag

[`Tag`](../../doc/models/tag.md)

## Example Usage

```php
$namespace = 'namespace2';

$repository = 'repository0';

$tag = 'tag6';

$repositoriesController = $client->getRepositoriesController();

try {
    $result = $repositoriesController->readrepositorytag(
        $namespace,
        $repository,
        $tag
    );
    echo 'Tag:';
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
| 403 | Forbidden | [`ErrorException`](../../doc/models/error-exception.md) |
| 404 | Not Found | [`ErrorException`](../../doc/models/error-exception.md) |

