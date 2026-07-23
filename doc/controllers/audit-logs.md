# Audit-Logs

The Audit Logs API endpoints allow you to query audit log events across a
namespace.

For more information, see [Audit Log](https://docs.docker.com/docker-hub/audit-log/)

```php
$auditLogsController = $client->getAuditLogsController();
```

## Class Name

`AuditLogsController`

## Methods

* [Audit Logs Get Audit Logs](../../doc/controllers/audit-logs.md#audit-logs-get-audit-logs)
* [Audit Logs Get Audit Actions](../../doc/controllers/audit-logs.md#audit-logs-get-audit-actions)


# Audit Logs Get Audit Logs

Get audit log events for a given namespace.

```php
function auditLogsGetAuditLogs(
    string $account,
    ?string $action = null,
    ?string $name = null,
    ?string $actor = null,
    ?\DateTime $from = null,
    ?\DateTime $to = null,
    ?int $page = 1,
    ?int $pageSize = 25
): V2AuditlogsResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `account` | `string` | Template, Required | Namespace to query audit logs for. |
| `action` | `?string` | Query, Optional | action name one of ["repo.tag.push", ...]. Optional parameter to filter specific audit log actions. |
| `name` | `?string` | Query, Optional | name. Optional parameter to filter audit log events to a specific name. For repository events, this is the name of the repository. For organization events, this is the name of the organization. For team member events, this is the username of the team member. |
| `actor` | `?string` | Query, Optional | actor name. Optional parameter to filter audit log events to the specific user who triggered the event. |
| `from` | `?DateTime` | Query, Optional | Start of the time window you wish to query audit events for. |
| `to` | `?DateTime` | Query, Optional | End of the time window you wish to query audit events for. |
| `page` | `?int` | Query, Optional | page - specify page number. Page number to get.<br><br>**Default**: `1` |
| `pageSize` | `?int` | Query, Optional | page_size - specify page size. Number of events to return per page.<br><br>**Default**: `25` |

## Response Type

**200**: A successful response.

[`V2AuditlogsResponse`](../../doc/models/v2-auditlogs-response.md)

## Example Usage

```php
$account = 'account0';

$page = 1;

$pageSize = 25;

$auditLogsController = $client->getAuditLogsController();

try {
    $result = $auditLogsController->auditLogsGetAuditLogs(
        $account,
        null,
        null,
        null,
        null,
        null,
        $page,
        $pageSize
    );
    echo 'V2AuditlogsResponse:';
    var_dump($result);
} catch (RpcStatusException $exp) {
    echo 'Caught RpcStatusException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "logs": [
    {
      "account": "docker",
      "action": "repo.tag.push",
      "action_description": "pushed the tag latest with the digest sha256:c1ae9c435032a to the repository docker/example",
      "actor": "docker",
      "data": {
        "digest": "sha256:c1ae9c435032a276f80220c7d9b40f76266bbe79243d34f9cda30b76fe114dfa",
        "tag": "latest"
      },
      "name": "docker/example",
      "timestamp": "2021-02-19T01:34:35Z"
    }
  ]
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 429 | - | `ApiException` |
| 500 | - | `ApiException` |
| Default | An unexpected error response. | [`RpcStatusException`](../../doc/models/rpc-status-exception.md) |


# Audit Logs Get Audit Actions

Get audit log actions for a namespace to be used as a filter for querying audit events.

```php
function auditLogsGetAuditActions(string $account): V2AuditlogsActionsResponse
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `account` | `string` | Template, Required | Namespace to query audit log actions for. |

## Response Type

**200**: A successful response.

[`V2AuditlogsActionsResponse`](../../doc/models/v2-auditlogs-actions-response.md)

## Example Usage

```php
$account = 'account0';

$auditLogsController = $client->getAuditLogsController();

try {
    $result = $auditLogsController->auditLogsGetAuditActions($account);
    echo 'V2AuditlogsActionsResponse:';
    var_dump($result);
} catch (RpcStatusException $exp) {
    echo 'Caught RpcStatusException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
{
  "actions": {
    "org": {
      "actions": [
        {
          "description": "contains team create events",
          "label": "Team Created",
          "name": "team.create"
        },
        {
          "description": "contains team delete events",
          "label": "Team Deleted",
          "name": "team.delete"
        },
        {
          "description": "contains team member add events",
          "label": "Team Member Added",
          "name": "team.member.add"
        },
        {
          "description": "contains team member remove events",
          "label": "Team Member Removed",
          "name": "team.member.remove"
        },
        {
          "description": "contains team member invite events",
          "label": "Team Member Invited",
          "name": "team.member.invite"
        },
        {
          "description": "contains org member remove events",
          "label": "Organization Member Removed",
          "name": "member.removed"
        },
        {
          "description": "contains organization create events",
          "label": "Organization Created",
          "name": "create"
        }
      ],
      "label": "Organization"
    },
    "repo": {
      "actions": [
        {
          "description": "contains repository create events",
          "label": "Repository Created",
          "name": "create"
        },
        {
          "description": "contains repository delete events",
          "label": "Repository Deleted",
          "name": "delete"
        },
        {
          "description": "contains repository privacy change events",
          "label": "Privacy Changed",
          "name": "change_privacy"
        },
        {
          "description": "contains image tag push events",
          "label": "Tag Pushed",
          "name": "tag.push"
        },
        {
          "description": "contains image tag delete events",
          "label": "Tag Deleted",
          "name": "tag.delete"
        }
      ],
      "label": "Repository"
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 429 | - | `ApiException` |
| 500 | - | `ApiException` |
| Default | An unexpected error response. | [`RpcStatusException`](../../doc/models/rpc-status-exception.md) |

