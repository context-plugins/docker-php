
# Client Class Documentation

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| version | `string` | *Default*: `'1.33'` |
| environment | [`Environment`](../README.md#environments) | The API environment. <br> **Default: `Environment.PRODUCTION`** |
| timeout | `int` | Timeout for API calls in seconds.<br>*Default*: `0` |
| enableRetries | `bool` | Whether to enable retries and backoff feature.<br>*Default*: `false` |
| numberOfRetries | `int` | The number of retries to make.<br>*Default*: `0` |
| retryInterval | `float` | The retry time interval between the endpoint calls.<br>*Default*: `1` |
| backOffFactor | `float` | Exponential backoff factor to increase interval between retries.<br>*Default*: `2` |
| maximumRetryWaitTime | `int` | The maximum wait time in seconds for overall retrying requests.<br>*Default*: `0` |
| retryOnTimeout | `bool` | Whether to retry on request timeout.<br>*Default*: `true` |
| httpStatusCodesToRetry | `array` | Http status codes to retry against.<br>*Default*: `408, 413, 429, 500, 502, 503, 504, 521, 522, 524, 408, 413, 429, 500, 502, 503, 504, 521, 522, 524` |
| httpMethodsToRetry | `array` | Http methods to retry against.<br>*Default*: `'GET', 'PUT', 'GET', 'PUT'` |
| proxyConfiguration | [`ProxyConfigurationBuilder`](../doc/proxy-configuration-builder.md) | Represents the proxy configurations for API calls |

The API client can be initialized as follows:

```php
use DockerLib\Environment;
use DockerLib\DockerClientBuilder;

$client = DockerClientBuilder::init()
    ->environment(Environment::PRODUCTION)
    ->version('1.33')
    ->build();
```

## Docker Client

The gateway for the SDK. This class acts as a factory for the Controllers and also holds the configuration of the SDK.

## Controllers

| Name | Description |
|  --- | --- |
| getContainerController() | Gets ContainerController |
| getImageController() | Gets ImageController |
| getNetworkController() | Gets NetworkController |
| getVolumeController() | Gets VolumeController |
| getExecController() | Gets ExecController |
| getSwarmController() | Gets SwarmController |
| getNodeController() | Gets NodeController |
| getServiceController() | Gets ServiceController |
| getTaskController() | Gets TaskController |
| getSecretController() | Gets SecretController |
| getConfigController() | Gets ConfigController |
| getPluginController() | Gets PluginController |
| getSystemController() | Gets SystemController |
| getDistributionController() | Gets DistributionController |
| getSessionExperimentalController() | Gets SessionExperimentalController |
| getAuthenticationController() | Gets AuthenticationController |
| getAccessTokensController() | Gets AccessTokensController |
| getImagesController() | Gets ImagesController |
| getAuditLogsController() | Gets AuditLogsController |
| getOrgSettingsController() | Gets OrgSettingsController |
| getRepositoriesController() | Gets RepositoriesController |
| getScimController() | Gets ScimController |
| getAPIController() | Gets APIController |

