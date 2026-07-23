# Secret

Secrets are sensitive data that can be used by services. Swarm mode must be enabled for these endpoints to work.

```php
$secretController = $client->getSecretController();
```

## Class Name

`SecretController`

## Methods

* [Secret List](../../doc/controllers/secret.md#secret-list)
* [Secret Create](../../doc/controllers/secret.md#secret-create)
* [Secret Delete](../../doc/controllers/secret.md#secret-delete)
* [Secret Inspect](../../doc/controllers/secret.md#secret-inspect)
* [Secret Update](../../doc/controllers/secret.md#secret-update)


# Secret List

```php
function secretList(?string $filters = null): array
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `filters` | `?string` | Query, Optional | A JSON encoded value of the filters (a `map[string][]string`) to process on the secrets list. Available filters:<br><br>- `id=<secret id>`<br>- `label=<key> or label=<key>=value`<br>- `name=<secret name>`<br>- `names=<secret name>` |

## Response Type

**200**: no error

[`Secret[]`](../../doc/models/secret.md)

## Example Usage

```php
$secretController = $client->getSecretController();

try {
    $result = $secretController->secretList();
    echo 'Secret[]:';
    var_dump($result);
} catch (Secrets500ErrorException $exp) {
    echo 'Caught Secrets500ErrorException:', $exp;
} catch (Secrets503ErrorException $exp) {
    echo 'Caught Secrets503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
[
  {
    "CreatedAt": "2017-07-20T13:55:28.678958722Z",
    "ID": "blt1owaxmitz71s9v5zh81zun",
    "Spec": {
      "Driver": {
        "Name": "secret-bucket",
        "Options": {
          "OptionA": "value for driver option A",
          "OptionB": "value for driver option B"
        }
      },
      "Labels": {
        "some.label": "some.value"
      },
      "Name": "mysql-passwd"
    },
    "UpdatedAt": "2017-07-20T13:55:28.678958722Z",
    "Version": {
      "Index": 85
    }
  },
  {
    "CreatedAt": "2016-11-05T01:20:17.327670065Z",
    "ID": "ktnbjxoalbkvbvedmg1urrz8h",
    "Spec": {
      "Labels": {
        "foo": "bar"
      },
      "Name": "app-dev.crt"
    },
    "UpdatedAt": "2016-11-05T01:20:17.327670065Z",
    "Version": {
      "Index": 11
    }
  }
]
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | server error | [`Secrets500ErrorException`](../../doc/models/secrets-500-error-exception.md) |
| 503 | node is not part of a swarm | [`Secrets503ErrorException`](../../doc/models/secrets-503-error-exception.md) |


# Secret Create

```php
function secretCreate(?SecretSpec $body = null): SecretsCreateResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `body` | [`?SecretSpec`](../../doc/models/secret-spec.md) | Body, Optional | - |

## Response Type

**201**: no error

[`SecretsCreateResponse`](../../doc/models/secrets-create-response.md)

## Example Usage

```php
$body = SecretSpecBuilder::init()
    ->labels(
        [
            'com.example.some-label' => 'some-value',
            'com.example.some-other-label' => 'some-other-value'
        ]
    )
    ->build();

$secretController = $client->getSecretController();

try {
    $result = $secretController->secretCreate($body);
    echo 'SecretsCreateResponse:';
    var_dump($result);
} catch (SecretsCreate409ErrorException $exp) {
    echo 'Caught SecretsCreate409ErrorException:', $exp;
} catch (SecretsCreate500ErrorException $exp) {
    echo 'Caught SecretsCreate500ErrorException:', $exp;
} catch (SecretsCreate503ErrorException $exp) {
    echo 'Caught SecretsCreate503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 409 | name conflicts with an existing object | [`SecretsCreate409ErrorException`](../../doc/models/secrets-create-409-error-exception.md) |
| 500 | server error | [`SecretsCreate500ErrorException`](../../doc/models/secrets-create-500-error-exception.md) |
| 503 | node is not part of a swarm | [`SecretsCreate503ErrorException`](../../doc/models/secrets-create-503-error-exception.md) |


# Secret Delete

```php
function secretDelete(string $id): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID of the secret |

## Response Type

**204**: no error

`void`

## Example Usage

```php
$id = 'id0';

$secretController = $client->getSecretController();

try {
    $secretController->secretDelete($id);
} catch (Secrets404ErrorException $exp) {
    echo 'Caught Secrets404ErrorException:', $exp;
} catch (Secrets500ErrorException $exp) {
    echo 'Caught Secrets500ErrorException:', $exp;
} catch (Secrets503ErrorException $exp) {
    echo 'Caught Secrets503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | secret not found | [`Secrets404ErrorException`](../../doc/models/secrets-404-error-exception.md) |
| 500 | server error | [`Secrets500ErrorException`](../../doc/models/secrets-500-error-exception.md) |
| 503 | node is not part of a swarm | [`Secrets503ErrorException`](../../doc/models/secrets-503-error-exception.md) |


# Secret Inspect

```php
function secretInspect(string $id): Secret
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID of the secret |

## Response Type

**200**: no error

[`Secret`](../../doc/models/secret.md)

## Example Usage

```php
$id = 'id0';

$secretController = $client->getSecretController();

try {
    $result = $secretController->secretInspect($id);
    echo 'Secret:';
    var_dump($result);
} catch (Secrets404ErrorException $exp) {
    echo 'Caught Secrets404ErrorException:', $exp;
} catch (Secrets500ErrorException $exp) {
    echo 'Caught Secrets500ErrorException:', $exp;
} catch (Secrets503ErrorException $exp) {
    echo 'Caught Secrets503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "CreatedAt": "2016-11-05T01:20:17.327670065Z",
  "ID": "ktnbjxoalbkvbvedmg1urrz8h",
  "Spec": {
    "Driver": {
      "Name": "secret-bucket",
      "Options": {
        "OptionA": "value for driver option A",
        "OptionB": "value for driver option B"
      }
    },
    "Labels": {
      "foo": "bar"
    },
    "Name": "app-dev.crt"
  },
  "UpdatedAt": "2016-11-05T01:20:17.327670065Z",
  "Version": {
    "Index": 11
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | secret not found | [`Secrets404ErrorException`](../../doc/models/secrets-404-error-exception.md) |
| 500 | server error | [`Secrets500ErrorException`](../../doc/models/secrets-500-error-exception.md) |
| 503 | node is not part of a swarm | [`Secrets503ErrorException`](../../doc/models/secrets-503-error-exception.md) |


# Secret Update

```php
function secretUpdate(string $id, int $version, ?SecretSpec $body = null): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID or name of the secret |
| `version` | `int` | Query, Required | The version number of the secret object being updated. This is required to avoid conflicting writes. |
| `body` | [`?SecretSpec`](../../doc/models/secret-spec.md) | Body, Optional | The spec of the secret to update. Currently, only the Labels field can be updated. All other fields must remain unchanged from the [SecretInspect endpoint](#operation/SecretInspect) response values. |

## Response Type

**200**: no error

`void`

## Example Usage

```php
$id = 'id0';

$version = 172;

$body = SecretSpecBuilder::init()
    ->labels(
        [
            'com.example.some-label' => 'some-value',
            'com.example.some-other-label' => 'some-other-value'
        ]
    )
    ->build();

$secretController = $client->getSecretController();

try {
    $secretController->secretUpdate(
        $id,
        $version,
        $body
    );
} catch (SecretsUpdate400ErrorException $exp) {
    echo 'Caught SecretsUpdate400ErrorException:', $exp;
} catch (SecretsUpdate404ErrorException $exp) {
    echo 'Caught SecretsUpdate404ErrorException:', $exp;
} catch (SecretsUpdate500ErrorException $exp) {
    echo 'Caught SecretsUpdate500ErrorException:', $exp;
} catch (SecretsUpdate503ErrorException $exp) {
    echo 'Caught SecretsUpdate503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | bad parameter | [`SecretsUpdate400ErrorException`](../../doc/models/secrets-update-400-error-exception.md) |
| 404 | no such secret | [`SecretsUpdate404ErrorException`](../../doc/models/secrets-update-404-error-exception.md) |
| 500 | server error | [`SecretsUpdate500ErrorException`](../../doc/models/secrets-update-500-error-exception.md) |
| 503 | node is not part of a swarm | [`SecretsUpdate503ErrorException`](../../doc/models/secrets-update-503-error-exception.md) |

