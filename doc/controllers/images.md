# Images

The Advanced Image Management API endpoints allow you to manage Docker
images across all repositories.

For more information, see [Advanced Image Management dashboard](https://docs.docker.com/docker-hub/image-management/).

```php
$imagesController = $client->getImagesController();
```

## Class Name

`ImagesController`

## Methods

* [Post Namespaces Delete Images](../../doc/controllers/images.md#post-namespaces-delete-images)
* [Get Namespaces Repositories Images](../../doc/controllers/images.md#get-namespaces-repositories-images)
* [Get Namespaces Repositories Images Summary](../../doc/controllers/images.md#get-namespaces-repositories-images-summary)
* [Get Namespaces Repositories Images Tags](../../doc/controllers/images.md#get-namespaces-repositories-images-tags)


# Post Namespaces Delete Images

Deletes one or more images within a namespace. This is currently limited to a single
repository.

If you attempt to delete images that are marked as active or are currently tagged, the deletion does not happen and it displays the warnings.
To continue with the deletion, you must ignore these warnings by putting them in the `ignore_warnings` property.

Deleting a currently tagged image deletes the tag from the repository.

You cannot ignore errors. It is not possible to directly delete children of multi-arch images.

```php
function postNamespacesDeleteImages(
    string $mNamespace,
    V2NamespacesDeleteImagesRequest $body
): V2NamespacesDeleteImagesResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `mNamespace` | `string` | Template, Required | Namespace of the repository. |
| `body` | [`V2NamespacesDeleteImagesRequest`](../../doc/models/v2-namespaces-delete-images-request.md) | Body, Required | Delete request. |

## Response Type

**200**: Deletion completed

[`V2NamespacesDeleteImagesResponse`](../../doc/models/v2-namespaces-delete-images-response.md)

## Example Usage

```php
$namespace = 'namespace2';

$body = V2NamespacesDeleteImagesRequestBuilder::init()
    ->activeFrom('12/01/2020 12:00:00')
    ->dryRun(false)
    ->build();

$imagesController = $client->getImagesController();

try {
    $result = $imagesController->postNamespacesDeleteImages(
        $namespace,
        $body
    );
    echo 'V2NamespacesDeleteImagesResponse:';
    var_dump($result);
} catch (V2NamespacesDeleteImages400ErrorException $exp) {
    echo 'Caught V2NamespacesDeleteImages400ErrorException:', $exp;
} catch (V2NamespacesDeleteImages403ErrorException $exp) {
    echo 'Caught V2NamespacesDeleteImages403ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Deletion not possible | [`V2NamespacesDeleteImages400ErrorException`](../../doc/models/v2-namespaces-delete-images-400-error-exception.md) |
| 403 | Forbidden - this API is only available to users on Pro or Team plans | [`V2NamespacesDeleteImages403ErrorException`](../../doc/models/v2-namespaces-delete-images-403-error-exception.md) |


# Get Namespaces Repositories Images

Gets details on the images in a repository.

```php
function getNamespacesRepositoriesImages(
    string $mNamespace,
    string $repository,
    ?string $status = null,
    ?bool $currentlyTagged = null,
    ?string $ordering = null,
    ?string $activeFrom = null,
    ?int $page = null,
    ?int $pageSize = null
): V2NamespacesRepositoriesImagesResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `mNamespace` | `string` | Template, Required | Namespace of the repository. |
| `repository` | `string` | Template, Required | Name of the repository. |
| `status` | [`?string(Status31Enum)`](../../doc/models/status-31-enum.md) | Query, Optional | Filters to only show images of this status. |
| `currentlyTagged` | `?bool` | Query, Optional | Filters to only show images with:<br><br>- `true`: at least 1 current tag.<br>- `false`: no current tags. |
| `ordering` | [`?string(Ordering1Enum)`](../../doc/models/ordering-1-enum.md) | Query, Optional | Orders the results by this property.<br><br>Prefixing with `-` sorts by descending order. |
| `activeFrom` | `?string` | Query, Optional | Sets the time from which an image must have been pushed or pulled to<br>be counted as active.<br><br>Defaults to 1 month before the current time. |
| `page` | `?int` | Query, Optional | Page number to get. Defaults to 1. |
| `pageSize` | `?int` | Query, Optional | Number of images to get per page. Defaults to 10. Max of 100. |

## Response Type

**200**: Success

[`V2NamespacesRepositoriesImagesResponse`](../../doc/models/v2-namespaces-repositories-images-response.md)

## Example Usage

```php
$namespace = 'namespace2';

$repository = 'repository0';

$imagesController = $client->getImagesController();

try {
    $result = $imagesController->getNamespacesRepositoriesImages(
        $namespace,
        $repository
    );
    echo 'V2NamespacesRepositoriesImagesResponse:';
    var_dump($result);
} catch (V2NamespacesRepositoriesImages401ErrorException $exp) {
    echo 'Caught V2NamespacesRepositoriesImages401ErrorException:', $exp;
} catch (V2NamespacesRepositoriesImages403ErrorException $exp) {
    echo 'Caught V2NamespacesRepositoriesImages403ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized - user does not have read access to the namespace. | [`V2NamespacesRepositoriesImages401ErrorException`](../../doc/models/v2-namespaces-repositories-images-401-error-exception.md) |
| 403 | Forbidden - this API is only available to users on Pro or Team plans. | [`V2NamespacesRepositoriesImages403ErrorException`](../../doc/models/v2-namespaces-repositories-images-403-error-exception.md) |


# Get Namespaces Repositories Images Summary

Gets the number of images in a repository and the number of images
counted as active and inactive.

```php
function getNamespacesRepositoriesImagesSummary(
    string $mNamespace,
    string $repository,
    ?string $activeFrom = null
): V2NamespacesRepositoriesImagesSummaryResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `mNamespace` | `string` | Template, Required | Namespace of the repository. |
| `repository` | `string` | Template, Required | Name of the repository. |
| `activeFrom` | `?string` | Query, Optional | Sets the time from which an image must have been pushed or pulled to<br>be counted as active.<br><br>Defaults to 1 month before the current time. |

## Response Type

**200**: Success

[`V2NamespacesRepositoriesImagesSummaryResponse`](../../doc/models/v2-namespaces-repositories-images-summary-response.md)

## Example Usage

```php
$namespace = 'namespace2';

$repository = 'repository0';

$imagesController = $client->getImagesController();

try {
    $result = $imagesController->getNamespacesRepositoriesImagesSummary(
        $namespace,
        $repository
    );
    echo 'V2NamespacesRepositoriesImagesSummaryResponse:';
    var_dump($result);
} catch (V2NamespacesRepositoriesImagesSummary401ErrorException $exp) {
    echo 'Caught V2NamespacesRepositoriesImagesSummary401ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized - user does not have read access to the namespace | [`V2NamespacesRepositoriesImagesSummary401ErrorException`](../../doc/models/v2-namespaces-repositories-images-summary-401-error-exception.md) |


# Get Namespaces Repositories Images Tags

Gets current and historical tags for an image.

```php
function getNamespacesRepositoriesImagesTags(
    string $mNamespace,
    string $repository,
    string $digest,
    ?int $page = null,
    ?int $pageSize = null
): V2NamespacesRepositoriesImagesDigestTagsResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `mNamespace` | `string` | Template, Required | Namespace of the repository. |
| `repository` | `string` | Template, Required | Name of the repository. |
| `digest` | `string` | Template, Required | Digest of the image. |
| `page` | `?int` | Query, Optional | Page number to get. Defaults to 1. |
| `pageSize` | `?int` | Query, Optional | Number of images to get per page. Defaults to 10. Max of 100. |

## Response Type

**200**: Success

[`V2NamespacesRepositoriesImagesDigestTagsResponse`](../../doc/models/v2-namespaces-repositories-images-digest-tags-response.md)

## Example Usage

```php
$namespace = 'namespace2';

$repository = 'repository0';

$digest = 'digest6';

$imagesController = $client->getImagesController();

try {
    $result = $imagesController->getNamespacesRepositoriesImagesTags(
        $namespace,
        $repository,
        $digest
    );
    echo 'V2NamespacesRepositoriesImagesDigestTagsResponse:';
    var_dump($result);
} catch (V2NamespacesRepositoriesImagesDigestTags401ErrorException $exp) {
    echo 'Caught V2NamespacesRepositoriesImagesDigestTags401ErrorException:', $exp;
} catch (V2NamespacesRepositoriesImagesDigestTags403ErrorException $exp) {
    echo 'Caught V2NamespacesRepositoriesImagesDigestTags403ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Unauthorized - user does not have read access to the namespace | [`V2NamespacesRepositoriesImagesDigestTags401ErrorException`](../../doc/models/v2-namespaces-repositories-images-digest-tags-401-error-exception.md) |
| 403 | Forbidden - this API is only available to users on Pro or Team plans | [`V2NamespacesRepositoriesImagesDigestTags403ErrorException`](../../doc/models/v2-namespaces-repositories-images-digest-tags-403-error-exception.md) |

