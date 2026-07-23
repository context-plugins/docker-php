# Image

```php
$imageController = $client->getImageController();
```

## Class Name

`ImageController`

## Methods

* [Image Build](../../doc/controllers/image.md#image-build)
* [Build Prune](../../doc/controllers/image.md#build-prune)
* [Image Commit](../../doc/controllers/image.md#image-commit)
* [Image Create](../../doc/controllers/image.md#image-create)
* [Image Get All](../../doc/controllers/image.md#image-get-all)
* [Image List](../../doc/controllers/image.md#image-list)
* [Image Load](../../doc/controllers/image.md#image-load)
* [Image Prune](../../doc/controllers/image.md#image-prune)
* [Image Search](../../doc/controllers/image.md#image-search)
* [Image Delete](../../doc/controllers/image.md#image-delete)
* [Image Get](../../doc/controllers/image.md#image-get)
* [Image History](../../doc/controllers/image.md#image-history)
* [Image Inspect](../../doc/controllers/image.md#image-inspect)
* [Image Push](../../doc/controllers/image.md#image-push)
* [Image Tag](../../doc/controllers/image.md#image-tag)


# Image Build

Build an image from a tar archive with a `Dockerfile` in it.

The `Dockerfile` specifies how the image is built from the tar archive. It is typically in the archive's root, but can be at a different path or have a different name by specifying the `dockerfile` parameter. [See the `Dockerfile` reference for more information](https://docs.docker.com/engine/reference/builder/).

The Docker daemon performs a preliminary validation of the `Dockerfile` before starting the build, and returns an error if the syntax is incorrect. After that, each instruction is run one-by-one until the ID of the new image is output.

The build is canceled if the client drops the connection by quitting or being killed.

```php
function imageBuild(
    ?string $dockerfile = 'Dockerfile',
    ?string $t = null,
    ?string $extrahosts = null,
    ?string $remote = null,
    ?bool $q = false,
    ?bool $nocache = false,
    ?string $cachefrom = null,
    ?string $pull = null,
    ?bool $rm = true,
    ?bool $forcerm = false,
    ?int $memory = null,
    ?int $memswap = null,
    ?int $cpushares = null,
    ?string $cpusetcpus = null,
    ?int $cpuperiod = null,
    ?int $cpuquota = null,
    ?int $buildargs = null,
    ?int $shmsize = null,
    ?bool $squash = null,
    ?string $labels = null,
    ?string $networkmode = null,
    ?string $contentType = null,
    ?string $xRegistryConfig = null,
    ?FileWrapper $body = null
): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `dockerfile` | `?string` | Query, Optional | Path within the build context to the `Dockerfile`. This is ignored if `remote` is specified and points to an external `Dockerfile`.<br><br>**Default**: `'Dockerfile'` |
| `t` | `?string` | Query, Optional | A name and optional tag to apply to the image in the `name:tag` format. If you omit the tag the default `latest` value is assumed. You can provide several `t` parameters. |
| `extrahosts` | `?string` | Query, Optional | Extra hosts to add to /etc/hosts |
| `remote` | `?string` | Query, Optional | A Git repository URI or HTTP/HTTPS context URI. If the URI points to a single text file, the file’s contents are placed into a file called `Dockerfile` and the image is built from that file. If the URI points to a tarball, the file is downloaded by the daemon and the contents therein used as the context for the build. If the URI points to a tarball and the `dockerfile` parameter is also specified, there must be a file with the corresponding path inside the tarball. |
| `q` | `?bool` | Query, Optional | Suppress verbose build output.<br><br>**Default**: `false` |
| `nocache` | `?bool` | Query, Optional | Do not use the cache when building the image.<br><br>**Default**: `false` |
| `cachefrom` | `?string` | Query, Optional | JSON array of images used for build cache resolution. |
| `pull` | `?string` | Query, Optional | Attempt to pull the image even if an older image exists locally. |
| `rm` | `?bool` | Query, Optional | Remove intermediate containers after a successful build.<br><br>**Default**: `true` |
| `forcerm` | `?bool` | Query, Optional | Always remove intermediate containers, even upon failure.<br><br>**Default**: `false` |
| `memory` | `?int` | Query, Optional | Set memory limit for build. |
| `memswap` | `?int` | Query, Optional | Total memory (memory + swap). Set as `-1` to disable swap. |
| `cpushares` | `?int` | Query, Optional | CPU shares (relative weight). |
| `cpusetcpus` | `?string` | Query, Optional | CPUs in which to allow execution (e.g., `0-3`, `0,1`). |
| `cpuperiod` | `?int` | Query, Optional | The length of a CPU period in microseconds. |
| `cpuquota` | `?int` | Query, Optional | Microseconds of CPU time that the container can get in a CPU period. |
| `buildargs` | `?int` | Query, Optional | JSON map of string pairs for build-time variables. Users pass these values at build-time. Docker uses the buildargs as the environment context for commands run via the `Dockerfile` RUN instruction, or for variable expansion in other `Dockerfile` instructions. This is not meant for passing secret values. [Read more about the buildargs instruction.](https://docs.docker.com/engine/reference/builder/#arg) |
| `shmsize` | `?int` | Query, Optional | Size of `/dev/shm` in bytes. The size must be greater than 0. If omitted the system uses 64MB. |
| `squash` | `?bool` | Query, Optional | Squash the resulting images layers into a single layer. *(Experimental release only.)* |
| `labels` | `?string` | Query, Optional | Arbitrary key/value labels to set on the image, as a JSON map of string pairs. |
| `networkmode` | `?string` | Query, Optional | Sets the networking mode for the run commands during build. Supported standard values are: `bridge`, `host`, `none`, and `container:<name\|id>`. Any other value is taken as a custom network's name to which this container should connect to. |
| `contentType` | [`?string(ContentTypeEnum)`](../../doc/models/content-type-enum.md) | Header, Optional | - |
| `xRegistryConfig` | `?string` | Header, Optional | This is a base64-encoded JSON object with auth configurations for multiple registries that a build may refer to.<br><br>The key is a registry URL, and the value is an auth configuration object, [as described in the authentication section](#section/Authentication). For example:<br><br>```<br>{<br>  "docker.example.com": {<br>    "username": "janedoe",<br>    "password": "hunter2"<br>  },<br>  "https://index.docker.io/v1/": {<br>    "username": "mobydock",<br>    "password": "conta1n3rize14"<br>  }<br>}<br>```<br><br>Only the registry domain name (and port if not the default 443) are required. However, for legacy reasons, the Docker Hub registry must be specified with both a `https://` prefix and a `/v1/` suffix even though Docker will prefer to use the v2 registry API. |
| `body` | [`?FileWrapper`](../../doc/models/file.md) | Form, Optional | A tar archive compressed with one of the following algorithms: identity (no compression), gzip, bzip2, xz. |

## Response Type

**200**: no error

`void`

## Example Usage

```php
$dockerfile = 'Dockerfile';

$q = false;

$nocache = false;

$rm = true;

$forcerm = false;

$imageController = $client->getImageController();

try {
    $imageController->imageBuild(
        $dockerfile,
        null,
        null,
        null,
        $q,
        $nocache,
        null,
        null,
        $rm,
        $forcerm
    );
} catch (Build400ErrorException $exp) {
    echo 'Caught Build400ErrorException:', $exp;
} catch (Build500ErrorException $exp) {
    echo 'Caught Build500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad parameter | [`Build400ErrorException`](../../doc/models/build-400-error-exception.md) |
| 500 | server error | [`Build500ErrorException`](../../doc/models/build-500-error-exception.md) |


# Build Prune

```php
function buildPrune(): BuildPruneResponse
```

## Response Type

**200**: No error

[`BuildPruneResponse`](../../doc/models/build-prune-response.md)

## Example Usage

```php
$imageController = $client->getImageController();

try {
    $result = $imageController->buildPrune();
    echo 'BuildPruneResponse:';
    var_dump($result);
} catch (BuildPrune500ErrorException $exp) {
    echo 'Caught BuildPrune500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | Server error | [`BuildPrune500ErrorException`](../../doc/models/build-prune-500-error-exception.md) |


# Image Commit

```php
function imageCommit(
    ?string $container = null,
    ?string $repo = null,
    ?string $tag = null,
    ?string $comment = null,
    ?string $author = null,
    ?bool $pause = true,
    ?string $changes = null,
    ?CommitRequest $body = null
): CommitResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `container` | `?string` | Query, Optional | The ID or name of the container to commit |
| `repo` | `?string` | Query, Optional | Repository name for the created image |
| `tag` | `?string` | Query, Optional | Tag name for the create image |
| `comment` | `?string` | Query, Optional | Commit message |
| `author` | `?string` | Query, Optional | Author of the image (e.g., `John Hannibal Smith <hannibal@a-team.com>`) |
| `pause` | `?bool` | Query, Optional | Whether to pause the container before committing<br><br>**Default**: `true` |
| `changes` | `?string` | Query, Optional | `Dockerfile` instructions to apply while committing |
| `body` | [`?CommitRequest`](../../doc/models/commit-request.md) | Body, Optional | The container configuration |

## Response Type

**201**: no error

[`CommitResponse`](../../doc/models/commit-response.md)

## Example Usage

```php
$pause = true;

$body = CommitRequestBuilder::init()
    ->attachStderr(true)
    ->attachStdin(false)
    ->attachStdout(true)
    ->openStdin(false)
    ->stdinOnce(false)
    ->stopSignal('SIGTERM')
    ->stopTimeout(10)
    ->tty(false)
    ->build();

$imageController = $client->getImageController();

try {
    $result = $imageController->imageCommit(
        null,
        null,
        null,
        null,
        null,
        $pause,
        null,
        $body
    );
    echo 'CommitResponse:';
    var_dump($result);
} catch (Commit404ErrorException $exp) {
    echo 'Caught Commit404ErrorException:', $exp;
} catch (Commit500ErrorException $exp) {
    echo 'Caught Commit500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | no such container | [`Commit404ErrorException`](../../doc/models/commit-404-error-exception.md) |
| 500 | server error | [`Commit500ErrorException`](../../doc/models/commit-500-error-exception.md) |


# Image Create

Create an image by either pulling it from a registry or importing it.

```php
function imageCreate(
    string $contentType,
    ?string $fromImage = null,
    ?string $fromSrc = null,
    ?string $repo = null,
    ?string $tag = null,
    ?string $xRegistryAuth = null,
    ?FileWrapper $body = null
): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `contentType` | [`string(ContentType1Enum)`](../../doc/models/content-type-1-enum.md) | Header, Required | - |
| `fromImage` | `?string` | Query, Optional | Name of the image to pull. The name may include a tag or digest. This parameter may only be used when pulling an image. The pull is cancelled if the HTTP connection is closed. |
| `fromSrc` | `?string` | Query, Optional | Source to import. The value may be a URL from which the image can be retrieved or `-` to read the image from the request body. This parameter may only be used when importing an image. |
| `repo` | `?string` | Query, Optional | Repository name given to an image when it is imported. The repo may include a tag. This parameter may only be used when importing an image. |
| `tag` | `?string` | Query, Optional | Tag or digest. If empty when pulling an image, this causes all tags for the given image to be pulled. |
| `xRegistryAuth` | `?string` | Header, Optional | A base64-encoded auth configuration. [See the authentication section for details.](#section/Authentication) |
| `body` | [`?FileWrapper`](../../doc/models/file.md) | Form, Optional | Image content if the value `-` has been specified in fromSrc query parameter |

## Response Type

**200**: no error

`void`

## Example Usage

```php
$contentType = ContentType1Enum::ENUM_APPLICATIONOCTETSTREAM;

$imageController = $client->getImageController();

try {
    $imageController->imageCreate($contentType);
} catch (ImagesCreate404ErrorException $exp) {
    echo 'Caught ImagesCreate404ErrorException:', $exp;
} catch (ImagesCreate500ErrorException $exp) {
    echo 'Caught ImagesCreate500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | repository does not exist or no read access | [`ImagesCreate404ErrorException`](../../doc/models/images-create-404-error-exception.md) |
| 500 | server error | [`ImagesCreate500ErrorException`](../../doc/models/images-create-500-error-exception.md) |


# Image Get All

Get a tarball containing all images and metadata for several image repositories.

For each value of the `names` parameter: if it is a specific name and tag (e.g. `ubuntu:latest`), then only that image (and its parents) are returned; if it is an image ID, similarly only that image (and its parents) are returned and there would be no names referenced in the 'repositories' file for this image ID.

For details on the format, see [the export image endpoint](#operation/ImageGet).

```php
function imageGetAll(?array $names = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `names` | `?(string[])` | Query, Optional | Image names to filter by |

## Response Type

**200**: no error

`mixed`

## Example Usage

```php
$imageController = $client->getImageController();

try {
    $result = $imageController->imageGetAll();
    echo 'mixed:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | server error | `ApiException` |


# Image List

Returns a list of images on the server. Note that it uses a different, smaller representation of an image than inspecting a single image.

```php
function imageList(?bool $all = false, ?string $filters = null, ?bool $digests = false): array
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `all` | `?bool` | Query, Optional | Show all images. Only images from a final layer (no children) are shown by default.<br><br>**Default**: `false` |
| `filters` | `?string` | Query, Optional | A JSON encoded value of the filters (a `map[string][]string`) to process on the images list. Available filters:<br><br>- `before`=(`<image-name>[:<tag>]`,  `<image id>` or `<image@digest>`)<br>- `dangling=true`<br>- `label=key` or `label="key=value"` of an image label<br>- `reference`=(`<image-name>[:<tag>]`)<br>- `since`=(`<image-name>[:<tag>]`,  `<image id>` or `<image@digest>`) |
| `digests` | `?bool` | Query, Optional | Show digest information as a `RepoDigests` field on each image.<br><br>**Default**: `false` |

## Response Type

**200**: Summary image data for the images matching the query

[`ImageSummary[]`](../../doc/models/image-summary.md)

## Example Usage

```php
$all = false;

$digests = false;

$imageController = $client->getImageController();

try {
    $result = $imageController->imageList(
        $all,
        null,
        $digests
    );
    echo 'ImageSummary[]:';
    var_dump($result);
} catch (ImagesJson500ErrorException $exp) {
    echo 'Caught ImagesJson500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
[
  {
    "Containers": 2,
    "Created": 1474925151,
    "Id": "sha256:e216a057b1cb1efc11f8a268f37ef62083e70b1b38323ba252e25ac88904a7e8",
    "Labels": {},
    "ParentId": "",
    "RepoDigests": [
      "ubuntu@sha256:992069aee4016783df6345315302fa59681aae51a8eeb2f889dea59290f21787"
    ],
    "RepoTags": [
      "ubuntu:12.04",
      "ubuntu:precise"
    ],
    "SharedSize": 0,
    "Size": 103579269,
    "VirtualSize": 103579269
  },
  {
    "Containers": 5,
    "Created": 1403128455,
    "Id": "sha256:3e314f95dcace0f5e4fd37b10862fe8398e3c60ed36600bc0ca5fda78b087175",
    "Labels": {},
    "ParentId": "",
    "RepoDigests": [
      "ubuntu@sha256:002fba3e3255af10be97ea26e476692a7ebed0bb074a9ab960b2e7a1526b15d7",
      "ubuntu@sha256:68ea0200f0b90df725d99d823905b04cf844f6039ef60c60bf3e019915017bd3"
    ],
    "RepoTags": [
      "ubuntu:12.10",
      "ubuntu:quantal"
    ],
    "SharedSize": 0,
    "Size": 172064416,
    "VirtualSize": 172064416
  }
]
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | server error | [`ImagesJson500ErrorException`](../../doc/models/images-json-500-error-exception.md) |


# Image Load

Load a set of images and tags into a repository.

For details on the format, see [the export image endpoint](#operation/ImageGet).

```php
function imageLoad(?bool $quiet = false, ?array $body = null): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `quiet` | `?bool` | Query, Optional | Suppress progress details during load.<br><br>**Default**: `false` |
| `body` | `?array` | Body, Optional | Tar archive containing images |

## Response Type

**200**: no error

`void`

## Example Usage

```php
$quiet = false;

$imageController = $client->getImageController();

try {
    $imageController->imageLoad($quiet);
} catch (ImagesLoad500ErrorException $exp) {
    echo 'Caught ImagesLoad500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | server error | [`ImagesLoad500ErrorException`](../../doc/models/images-load-500-error-exception.md) |


# Image Prune

```php
function imagePrune(?string $filters = null): ImagesPruneResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `filters` | `?string` | Query, Optional | Filters to process on the prune list, encoded as JSON (a `map[string][]string`). Available filters:<br><br>- `dangling=<boolean>` When set to `true` (or `1`), prune only<br>  unused *and* untagged images. When set to `false`<br>  (or `0`), all unused images are pruned.<br>- `until=<string>` Prune images created before this timestamp. The `<timestamp>` can be Unix timestamps, date formatted timestamps, or Go duration strings (e.g. `10m`, `1h30m`) computed relative to the daemon machine’s time.<br>- `label` (`label=<key>`, `label=<key>=<value>`, `label!=<key>`, or `label!=<key>=<value>`) Prune images with (or without, in case `label!=...` is used) the specified labels. |

## Response Type

**200**: No error

[`ImagesPruneResponse`](../../doc/models/images-prune-response.md)

## Example Usage

```php
$imageController = $client->getImageController();

try {
    $result = $imageController->imagePrune();
    echo 'ImagesPruneResponse:';
    var_dump($result);
} catch (ImagesPrune500ErrorException $exp) {
    echo 'Caught ImagesPrune500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | Server error | [`ImagesPrune500ErrorException`](../../doc/models/images-prune-500-error-exception.md) |


# Image Search

Search for an image on Docker Hub.

```php
function imageSearch(string $term, ?int $limit = null, ?string $filters = null): array
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `term` | `string` | Query, Required | Term to search |
| `limit` | `?int` | Query, Optional | Maximum number of results to return |
| `filters` | `?string` | Query, Optional | A JSON encoded value of the filters (a `map[string][]string`) to process on the images list. Available filters:<br><br>- `is-automated=(true\|false)`<br>- `is-official=(true\|false)`<br>- `stars=<number>` Matches images that has at least 'number' stars. |

## Response Type

**200**: No error

[`ImagesSearchResponse[]`](../../doc/models/images-search-response.md)

## Example Usage

```php
$term = 'term6';

$imageController = $client->getImageController();

try {
    $result = $imageController->imageSearch($term);
    echo 'ImagesSearchResponse[]:';
    var_dump($result);
} catch (ImagesSearch500ErrorException $exp) {
    echo 'Caught ImagesSearch500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
[
  {
    "description": "",
    "is_automated": false,
    "is_official": false,
    "name": "wma55/u1210sshd",
    "star_count": 0
  },
  {
    "description": "",
    "is_automated": false,
    "is_official": false,
    "name": "jdswinbank/sshd",
    "star_count": 0
  },
  {
    "description": "",
    "is_automated": false,
    "is_official": false,
    "name": "vgauthier/sshd",
    "star_count": 0
  }
]
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | Server error | [`ImagesSearch500ErrorException`](../../doc/models/images-search-500-error-exception.md) |


# Image Delete

Remove an image, along with any untagged parent images that were
referenced by that image.

Images can't be removed if they have descendant images, are being
used by a running container or are being used by a build.

```php
function imageDelete(string $name, ?bool $force = false, ?bool $noprune = false): array
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Template, Required | Image name or ID |
| `force` | `?bool` | Query, Optional | Remove the image even if it is being used by stopped containers or has other tags<br><br>**Default**: `false` |
| `noprune` | `?bool` | Query, Optional | Do not delete untagged parent images<br><br>**Default**: `false` |

## Response Type

**200**: The image was deleted successfully

[`ImageDeleteResponseItem[]`](../../doc/models/image-delete-response-item.md)

## Example Usage

```php
$name = 'name0';

$force = false;

$noprune = false;

$imageController = $client->getImageController();

try {
    $result = $imageController->imageDelete(
        $name,
        $force,
        $noprune
    );
    echo 'ImageDeleteResponseItem[]:';
    var_dump($result);
} catch (Images404ErrorException $exp) {
    echo 'Caught Images404ErrorException:', $exp;
} catch (Images409ErrorException $exp) {
    echo 'Caught Images409ErrorException:', $exp;
} catch (Images500ErrorException $exp) {
    echo 'Caught Images500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
[
  {
    "Untagged": "3e2f21a89f"
  },
  {
    "Deleted": "3e2f21a89f"
  },
  {
    "Deleted": "53b4f83ac9"
  }
]
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | No such image | [`Images404ErrorException`](../../doc/models/images-404-error-exception.md) |
| 409 | Conflict | [`Images409ErrorException`](../../doc/models/images-409-error-exception.md) |
| 500 | Server error | [`Images500ErrorException`](../../doc/models/images-500-error-exception.md) |


# Image Get

Get a tarball containing all images and metadata for a repository.

If `name` is a specific name and tag (e.g. `ubuntu:latest`), then only that image (and its parents) are returned. If `name` is an image ID, similarly only that image (and its parents) are returned, but with the exclusion of the `repositories` file in the tarball, as there were no image names referenced.

### Image tarball format

An image tarball contains one directory per image layer (named using its long ID), each containing these files:

- `VERSION`: currently `1.0` - the file format version
- `json`: detailed layer information, similar to `docker inspect layer_id`
- `layer.tar`: A tarfile containing the filesystem changes in this layer

The `layer.tar` file contains `aufs` style `.wh..wh.aufs` files and directories for storing attribute changes and deletions.

If the tarball defines a repository, the tarball should also include a `repositories` file at the root that contains a list of repository and tag names mapped to layer IDs.

```json
{
  "hello-world": {
    "latest": "565a9d68a73f6706862bfe8409a7f659776d4d60a8d096eb4a3cbce6999cc2a1"
  }
}
```

```php
function imageGet(string $name)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Template, Required | Image name or ID |

## Response Type

**200**: no error

`mixed`

## Example Usage

```php
$name = 'name0';

$imageController = $client->getImageController();

try {
    $result = $imageController->imageGet($name);
    echo 'mixed:';
    var_dump($result);
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | server error | `ApiException` |


# Image History

Return parent layers of an image.

```php
function imageHistory(string $name): array
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Template, Required | Image name or ID |

## Response Type

**200**: List of image layers

[`ImagesHistoryResponse[]`](../../doc/models/images-history-response.md)

## Example Usage

```php
$name = 'name0';

$imageController = $client->getImageController();

try {
    $result = $imageController->imageHistory($name);
    echo 'ImagesHistoryResponse[]:';
    var_dump($result);
} catch (ImagesHistory404ErrorException $exp) {
    echo 'Caught ImagesHistory404ErrorException:', $exp;
} catch (ImagesHistory500ErrorException $exp) {
    echo 'Caught ImagesHistory500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
[
  {
    "Comment": "",
    "Created": 1398108230,
    "CreatedBy": "/bin/sh -c #(nop) ADD file:eb15dbd63394e063b805a3c32ca7bf0266ef64676d5a6fab4801f2e81e2a5148 in /",
    "Id": "3db9c44f45209632d6050b35958829c3a2aa256d81b9a7be45b362ff85c54710",
    "Size": 182964289,
    "Tags": [
      "ubuntu:lucid",
      "ubuntu:10.04"
    ]
  },
  {
    "Comment": "",
    "Created": 1398108222,
    "CreatedBy": "/bin/sh -c #(nop) MAINTAINER Tianon Gravi <admwiggin@gmail.com> - mkimage-debootstrap.sh -i iproute,iputils-ping,ubuntu-minimal -t lucid.tar.xz lucid http://archive.ubuntu.com/ubuntu/",
    "Id": "6cfa4d1f33fb861d4d114f43b25abd0ac737509268065cdfd69d544a59c85ab8",
    "Size": 0,
    "Tags": []
  },
  {
    "Comment": "Imported from -",
    "Created": 1371157430,
    "CreatedBy": "",
    "Id": "511136ea3c5a64f264b78b5433614aec563103b4d4702f3ba7d4d2698e22c158",
    "Size": 0,
    "Tags": [
      "scratch12:latest",
      "scratch:latest"
    ]
  }
]
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | No such image | [`ImagesHistory404ErrorException`](../../doc/models/images-history-404-error-exception.md) |
| 500 | Server error | [`ImagesHistory500ErrorException`](../../doc/models/images-history-500-error-exception.md) |


# Image Inspect

Return low-level information about an image.

```php
function imageInspect(string $name): Image
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Template, Required | Image name or id |

## Response Type

**200**: No error

[`Image`](../../doc/models/image.md)

## Example Usage

```php
$name = 'name0';

$imageController = $client->getImageController();

try {
    $result = $imageController->imageInspect($name);
    echo 'Image:';
    var_dump($result);
} catch (ImagesJson404ErrorException $exp) {
    echo 'Caught ImagesJson404ErrorException:', $exp;
} catch (ImagesJson500ErrorException $exp) {
    echo 'Caught ImagesJson500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "Architecture": "amd64",
  "Author": "",
  "Comment": "",
  "Config": {
    "AttachStderr": false,
    "AttachStdin": false,
    "AttachStdout": false,
    "Cmd": [
      "/bin/bash"
    ],
    "Domainname": "",
    "Env": [
      "PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
    ],
    "Hostname": "e611e15f9c9d",
    "Image": "91e54dfb11794fad694460162bf0cb0a4fa710cfa3f60979c177d920813e267c",
    "Labels": {
      "com.example.license": "GPL",
      "com.example.vendor": "Acme",
      "com.example.version": "1.0"
    },
    "MacAddress": "",
    "NetworkDisabled": false,
    "OnBuild": [],
    "OpenStdin": false,
    "PublishService": "",
    "StdinOnce": false,
    "Tty": false,
    "User": "",
    "WorkingDir": ""
  },
  "Container": "cb91e48a60d01f1e27028b4fc6819f4f290b3cf12496c8176ec714d0d390984a",
  "ContainerConfig": {
    "AttachStderr": false,
    "AttachStdin": false,
    "AttachStdout": false,
    "Cmd": [
      "/bin/sh",
      "-c",
      "#(nop) LABEL com.example.vendor=Acme com.example.license=GPL com.example.version=1.0"
    ],
    "Domainname": "",
    "Env": [
      "PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
    ],
    "Hostname": "e611e15f9c9d",
    "Image": "91e54dfb11794fad694460162bf0cb0a4fa710cfa3f60979c177d920813e267c",
    "Labels": {
      "com.example.license": "GPL",
      "com.example.vendor": "Acme",
      "com.example.version": "1.0"
    },
    "MacAddress": "",
    "NetworkDisabled": false,
    "OnBuild": [],
    "OpenStdin": false,
    "PublishService": "",
    "StdinOnce": false,
    "Tty": false,
    "User": "",
    "WorkingDir": ""
  },
  "Created": "2015-09-10T08:30:53.26995814Z",
  "DockerVersion": "1.9.0-dev",
  "GraphDriver": {
    "Data": {},
    "Name": "aufs"
  },
  "Id": "sha256:85f05633ddc1c50679be2b16a0479ab6f7637f8884e0cfe0f4d20e1ebb3d6e7c",
  "Os": "linux",
  "Parent": "sha256:91e54dfb11794fad694460162bf0cb0a4fa710cfa3f60979c177d920813e267c",
  "RepoDigests": [
    "localhost:5000/test/busybox/example@sha256:cbbf2f9a99b47fc460d422812b6a5adff7dfee951d8fa2e4a98caa0382cfbdbf"
  ],
  "RepoTags": [
    "example:1.0",
    "example:latest",
    "example:stable"
  ],
  "RootFS": {
    "Layers": [
      "sha256:1834950e52ce4d5a88a1bbd131c537f4d0e56d10ff0dd69e66be3b7dfa9df7e6",
      "sha256:5f70bf18a086007016e948b04aed3b82103a36bea41755b6cddfaf10ace3c6ef"
    ],
    "Type": "layers"
  },
  "Size": 0,
  "VirtualSize": 188359297
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | No such image | [`ImagesJson404ErrorException`](../../doc/models/images-json-404-error-exception.md) |
| 500 | Server error | [`ImagesJson500ErrorException`](../../doc/models/images-json-500-error-exception.md) |


# Image Push

Push an image to a registry.

If you wish to push an image on to a private registry, that image must already have a tag which references the registry. For example, `registry.example.com/myimage:latest`.

The push is cancelled if the HTTP connection is closed.

```php
function imagePush(string $name, string $xRegistryAuth, ?string $tag = null): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Template, Required | Image name or ID. |
| `xRegistryAuth` | `string` | Header, Required | A base64-encoded auth configuration. [See the authentication section for details.](#section/Authentication) |
| `tag` | `?string` | Query, Optional | The tag to associate with the image on the registry. |

## Response Type

**200**: No error

`void`

## Example Usage

```php
$name = 'name0';

$xRegistryAuth = 'X-Registry-Auth8';

$imageController = $client->getImageController();

try {
    $imageController->imagePush(
        $name,
        $xRegistryAuth
    );
} catch (ImagesPush404ErrorException $exp) {
    echo 'Caught ImagesPush404ErrorException:', $exp;
} catch (ImagesPush500ErrorException $exp) {
    echo 'Caught ImagesPush500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | No such image | [`ImagesPush404ErrorException`](../../doc/models/images-push-404-error-exception.md) |
| 500 | Server error | [`ImagesPush500ErrorException`](../../doc/models/images-push-500-error-exception.md) |


# Image Tag

Tag an image so that it becomes part of a repository.

```php
function imageTag(string $name, ?string $repo = null, ?string $tag = null): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Template, Required | Image name or ID to tag. |
| `repo` | `?string` | Query, Optional | The repository to tag in. For example, `someuser/someimage`. |
| `tag` | `?string` | Query, Optional | The name of the new tag. |

## Response Type

**201**: No error

`void`

## Example Usage

```php
$name = 'name0';

$imageController = $client->getImageController();

try {
    $imageController->imageTag($name);
} catch (ImagesTag400ErrorException $exp) {
    echo 'Caught ImagesTag400ErrorException:', $exp;
} catch (ImagesTag404ErrorException $exp) {
    echo 'Caught ImagesTag404ErrorException:', $exp;
} catch (ImagesTag409ErrorException $exp) {
    echo 'Caught ImagesTag409ErrorException:', $exp;
} catch (ImagesTag500ErrorException $exp) {
    echo 'Caught ImagesTag500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | Bad parameter | [`ImagesTag400ErrorException`](../../doc/models/images-tag-400-error-exception.md) |
| 404 | No such image | [`ImagesTag404ErrorException`](../../doc/models/images-tag-404-error-exception.md) |
| 409 | Conflict | [`ImagesTag409ErrorException`](../../doc/models/images-tag-409-error-exception.md) |
| 500 | Server error | [`ImagesTag500ErrorException`](../../doc/models/images-tag-500-error-exception.md) |

