# API

```php
$aPIController = $client->getAPIController();
```

## Class Name

`APIController`


# Task Logs

Get `stdout` and `stderr` logs from a task.

**Note**: This endpoint works only for services with the `json-file` or `journald` logging drivers.

```php
function taskLogs(
    string $id,
    ?bool $details = false,
    ?bool $follow = false,
    ?bool $stdout = false,
    ?bool $stderr = false,
    ?int $since = 0,
    ?bool $timestamps = false,
    ?string $tail = 'all'
): string
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID of the task |
| `details` | `?bool` | Query, Optional | Show task context and extra details provided to logs.<br><br>**Default**: `false` |
| `follow` | `?bool` | Query, Optional | Return the logs as a stream.<br><br>This will return a `101` HTTP response with a `Connection: upgrade` header, then hijack the HTTP connection to send raw output. For more information about hijacking and the stream format, [see the documentation for the attach endpoint](#operation/ContainerAttach).<br><br>**Default**: `false` |
| `stdout` | `?bool` | Query, Optional | Return logs from `stdout`<br><br>**Default**: `false` |
| `stderr` | `?bool` | Query, Optional | Return logs from `stderr`<br><br>**Default**: `false` |
| `since` | `?int` | Query, Optional | Only return logs since this time, as a UNIX timestamp<br><br>**Default**: `0` |
| `timestamps` | `?bool` | Query, Optional | Add timestamps to every log line<br><br>**Default**: `false` |
| `tail` | `?string` | Query, Optional | Only return this number of log lines from the end of the logs. Specify as an integer or `all` to output all log lines.<br><br>**Default**: `'all'` |

## Response Type

**200**: logs returned as a string in response body

`string`

## Example Usage

```php
$id = 'id0';

$details = false;

$follow = false;

$stdout = false;

$stderr = false;

$since = 0;

$timestamps = false;

$tail = 'all';

$aPIController = $client->getAPIController();

try {
    $result = $aPIController->taskLogs(
        $id,
        $details,
        $follow,
        $stdout,
        $stderr,
        $since,
        $timestamps,
        $tail
    );
    echo 'string:';
    var_dump($result);
} catch (TasksLogs404ErrorException $exp) {
    echo 'Caught TasksLogs404ErrorException:', $exp;
} catch (TasksLogs500ErrorException $exp) {
    echo 'Caught TasksLogs500ErrorException:', $exp;
} catch (TasksLogs503ErrorException $exp) {
    echo 'Caught TasksLogs503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | no such task | [`TasksLogs404ErrorException`](../../doc/models/tasks-logs-404-error-exception.md) |
| 500 | server error | [`TasksLogs500ErrorException`](../../doc/models/tasks-logs-500-error-exception.md) |
| 503 | node is not part of a swarm | [`TasksLogs503ErrorException`](../../doc/models/tasks-logs-503-error-exception.md) |

