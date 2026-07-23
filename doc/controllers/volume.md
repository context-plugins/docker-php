# Volume

Create and manage persistent storage that can be attached to containers.

```php
$volumeController = $client->getVolumeController();
```

## Class Name

`VolumeController`

## Methods

* [Volume List](../../doc/controllers/volume.md#volume-list)
* [Volume Create](../../doc/controllers/volume.md#volume-create)
* [Volume Prune](../../doc/controllers/volume.md#volume-prune)
* [Volume Delete](../../doc/controllers/volume.md#volume-delete)
* [Volume Inspect](../../doc/controllers/volume.md#volume-inspect)


# Volume List

```php
function volumeList(?string $filters = null): VolumesResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `filters` | `?string` | Query, Optional | JSON encoded value of the filters (a `map[string][]string`) to<br>process on the volumes list. Available filters:<br><br>- `dangling=<boolean>` When set to `true` (or `1`), returns all<br>  volumes that are not in use by a container. When set to `false`<br>  (or `0`), only volumes that are in use by one or more<br>  containers are returned.<br>- `driver=<volume-driver-name>` Matches volumes based on their driver.<br>- `label=<key>` or `label=<key>:<value>` Matches volumes based on<br>  the presence of a `label` alone or a `label` and a value.<br>- `name=<volume-name>` Matches all or part of a volume name. |

## Response Type

**200**: Summary volume data that matches the query

[`VolumesResponse`](../../doc/models/volumes-response.md)

## Example Usage

```php
$volumeController = $client->getVolumeController();

try {
    $result = $volumeController->volumeList();
    echo 'VolumesResponse:';
    var_dump($result);
} catch (Volumes500ErrorException $exp) {
    echo 'Caught Volumes500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "Volumes": [
    {
      "CreatedAt": "2017-07-19T12:00:26Z",
      "Driver": "local",
      "Labels": {
        "com.example.some-label": "some-value",
        "com.example.some-other-label": "some-other-value"
      },
      "Mountpoint": "/var/lib/docker/volumes/tardis",
      "Name": "tardis",
      "Options": {
        "device": "tmpfs",
        "o": "size=100m,uid=1000",
        "type": "tmpfs"
      },
      "Scope": "local"
    }
  ],
  "Warnings": []
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | Server error | [`Volumes500ErrorException`](../../doc/models/volumes-500-error-exception.md) |


# Volume Create

```php
function volumeCreate(VolumesCreateRequest $body): Volume
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`VolumesCreateRequest`](../../doc/models/volumes-create-request.md) | Body, Required | Volume configuration |

## Response Type

**201**: The volume was created successfully

[`Volume`](../../doc/models/volume.md)

## Example Usage

```php
$body = VolumesCreateRequestBuilder::init()
    ->driver('custom')
    ->labels(
        [
            'com.example.some-label' => 'some-value',
            'com.example.some-other-label' => 'some-other-value'
        ]
    )
    ->name('tardis')
    ->build();

$volumeController = $client->getVolumeController();

try {
    $result = $volumeController->volumeCreate($body);
    echo 'Volume:';
    var_dump($result);
} catch (VolumesCreate500ErrorException $exp) {
    echo 'Caught VolumesCreate500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | Server error | [`VolumesCreate500ErrorException`](../../doc/models/volumes-create-500-error-exception.md) |


# Volume Prune

```php
function volumePrune(?string $filters = null): VolumesPruneResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `filters` | `?string` | Query, Optional | Filters to process on the prune list, encoded as JSON (a `map[string][]string`).<br><br>Available filters:<br><br>- `label` (`label=<key>`, `label=<key>=<value>`, `label!=<key>`, or `label!=<key>=<value>`) Prune volumes with (or without, in case `label!=...` is used) the specified labels. |

## Response Type

**200**: No error

[`VolumesPruneResponse`](../../doc/models/volumes-prune-response.md)

## Example Usage

```php
$volumeController = $client->getVolumeController();

try {
    $result = $volumeController->volumePrune();
    echo 'VolumesPruneResponse:';
    var_dump($result);
} catch (VolumesPrune500ErrorException $exp) {
    echo 'Caught VolumesPrune500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | Server error | [`VolumesPrune500ErrorException`](../../doc/models/volumes-prune-500-error-exception.md) |


# Volume Delete

Instruct the driver to remove the volume.

```php
function volumeDelete(string $name, ?bool $force = false): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Template, Required | Volume name or ID |
| `force` | `?bool` | Query, Optional | Force the removal of the volume<br><br>**Default**: `false` |

## Response Type

**204**: The volume was removed

`void`

## Example Usage

```php
$name = 'name0';

$force = false;

$volumeController = $client->getVolumeController();

try {
    $volumeController->volumeDelete(
        $name,
        $force
    );
} catch (Volumes404ErrorException $exp) {
    echo 'Caught Volumes404ErrorException:', $exp;
} catch (Volumes409ErrorException $exp) {
    echo 'Caught Volumes409ErrorException:', $exp;
} catch (Volumes500ErrorException $exp) {
    echo 'Caught Volumes500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | No such volume or volume driver | [`Volumes404ErrorException`](../../doc/models/volumes-404-error-exception.md) |
| 409 | Volume is in use and cannot be removed | [`Volumes409ErrorException`](../../doc/models/volumes-409-error-exception.md) |
| 500 | Server error | [`Volumes500ErrorException`](../../doc/models/volumes-500-error-exception.md) |


# Volume Inspect

```php
function volumeInspect(string $name): Volume
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Template, Required | Volume name or ID |

## Response Type

**200**: No error

[`Volume`](../../doc/models/volume.md)

## Example Usage

```php
$name = 'name0';

$volumeController = $client->getVolumeController();

try {
    $result = $volumeController->volumeInspect($name);
    echo 'Volume:';
    var_dump($result);
} catch (Volumes404ErrorException $exp) {
    echo 'Caught Volumes404ErrorException:', $exp;
} catch (Volumes500ErrorException $exp) {
    echo 'Caught Volumes500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | No such volume | [`Volumes404ErrorException`](../../doc/models/volumes-404-error-exception.md) |
| 500 | Server error | [`Volumes500ErrorException`](../../doc/models/volumes-500-error-exception.md) |

