# Org-Settings

The Org Settings API endpoints allow you to manage your organization's
settings.

```php
$orgSettingsController = $client->getOrgSettingsController();
```

## Class Name

`OrgSettingsController`

## Methods

* [Getorganizationsettings](../../doc/controllers/org-settings.md#getorganizationsettings)
* [Updateorganizationsettings](../../doc/controllers/org-settings.md#updateorganizationsettings)


# Getorganizationsettings

Returns organization settings by name.

```php
function getorganizationsettings(string $name): OrgSettings
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Template, Required | Name of the organization. |

## Response Type

**200**: OK

[`OrgSettings`](../../doc/models/org-settings.md)

## Example Usage

```php
$name = 'name0';

$orgSettingsController = $client->getOrgSettingsController();

try {
    $result = $orgSettingsController->getorganizationsettings($name);
    echo 'OrgSettings:';
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
| 403 | Forbidden | [`ErrorException`](../../doc/models/error-exception.md) |
| 404 | Not Found | [`ErrorException`](../../doc/models/error-exception.md) |


# Updateorganizationsettings

Updates an organization's settings. Some settings are only used when the
organization is on a business plan.

***Only users in the "owners" group of the organization can use this endpoint.***

The following settings are only used on a business plan:

- `restricted_images`

```php
function updateorganizationsettings(string $name, V2OrgsSettingsRequest $body): OrgSettings
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Template, Required | Name of the organization. |
| `body` | [`V2OrgsSettingsRequest`](../../doc/models/v2-orgs-settings-request.md) | Body, Required | - |

## Response Type

**200**: OK

[`OrgSettings`](../../doc/models/org-settings.md)

## Example Usage

```php
$name = 'name0';

$body = V2OrgsSettingsRequestBuilder::init(
    RestrictedImages1Builder::init(
        true,
        true,
        true
    )->build()
)->build();

$orgSettingsController = $client->getOrgSettingsController();

try {
    $result = $orgSettingsController->updateorganizationsettings(
        $name,
        $body
    );
    echo 'OrgSettings:';
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
| 403 | Forbidden | [`ErrorException`](../../doc/models/error-exception.md) |
| 404 | Not Found | [`ErrorException`](../../doc/models/error-exception.md) |

