# Distribution

```php
$distributionController = $client->getDistributionController();
```

## Class Name

`DistributionController`


# Distribution Inspect

Return image digest and platform information by contacting the registry.

```php
function distributionInspect(string $name): DistributionJsonResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `name` | `string` | Template, Required | Image name or id |

## Response Type

**200**: descriptor and platform information

[`DistributionJsonResponse`](../../doc/models/distribution-json-response.md)

## Example Usage

```php
$name = 'name0';

$distributionController = $client->getDistributionController();

try {
    $result = $distributionController->distributionInspect($name);
    echo 'DistributionJsonResponse:';
    var_dump($result);
} catch (DistributionJson401ErrorException $exp) {
    echo 'Caught DistributionJson401ErrorException:', $exp;
} catch (DistributionJson500ErrorException $exp) {
    echo 'Caught DistributionJson500ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "Descriptor": {
    "Digest": "sha256:c0537ff6a5218ef531ece93d4984efc99bbf3f7497c0a7726c88e2bb7584dc96",
    "MediaType": "application/vnd.docker.distribution.manifest.v2+json",
    "Size": 3987495,
    "URLs": [
      ""
    ]
  },
  "Platforms": [
    {
      "Architecture": "amd64",
      "Features": [
        ""
      ],
      "OS": "linux",
      "OSFeatures": [
        ""
      ],
      "OSVersion": "",
      "Variant": ""
    }
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 401 | Failed authentication or no image found | [`DistributionJson401ErrorException`](../../doc/models/distribution-json-401-error-exception.md) |
| 500 | Server error | [`DistributionJson500ErrorException`](../../doc/models/distribution-json-500-error-exception.md) |

