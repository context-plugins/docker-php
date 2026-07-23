# Task

A task is a container running on a swarm. It is the atomic scheduling unit of swarm. Swarm mode must be enabled for these endpoints to work.

```php
$taskController = $client->getTaskController();
```

## Class Name

`TaskController`

## Methods

* [Task List](../../doc/controllers/task.md#task-list)
* [Task Inspect](../../doc/controllers/task.md#task-inspect)


# Task List

```php
function taskList(?string $filters = null): array
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `filters` | `?string` | Query, Optional | A JSON encoded value of the filters (a `map[string][]string`) to process on the tasks list. Available filters:<br><br>- `desired-state=(running \| shutdown \| accepted)`<br>- `id=<task id>`<br>- `label=key` or `label="key=value"`<br>- `name=<task name>`<br>- `node=<node id or name>`<br>- `service=<service name>` |

## Response Type

**200**: no error

[`Task[]`](../../doc/models/task.md)

## Example Usage

```php
$taskController = $client->getTaskController();

try {
    $result = $taskController->taskList();
    echo 'Task[]:';
    var_dump($result);
} catch (Tasks500ErrorException $exp) {
    echo 'Caught Tasks500ErrorException:', $exp;
} catch (Tasks503ErrorException $exp) {
    echo 'Caught Tasks503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Example Response *(as JSON)*

```json
[
  {
    "CreatedAt": "2016-06-07T21:07:31.171892745Z",
    "DesiredState": "running",
    "ID": "0kzzo1i0y4jz6027t0k7aezc7",
    "NetworksAttachments": [
      {
        "Addresses": [
          "10.255.0.10/16"
        ],
        "Network": {
          "CreatedAt": "2016-06-07T20:31:11.912919752Z",
          "DriverState": {
            "Name": "overlay",
            "Options": {
              "com.docker.network.driver.overlay.vxlanid_list": "256"
            }
          },
          "ID": "4qvuz4ko70xaltuqbt8956gd1",
          "IPAMOptions": {
            "Configs": [
              {
                "Gateway": "10.255.0.1",
                "Subnet": "10.255.0.0/16"
              }
            ],
            "Driver": {
              "Name": "default"
            }
          },
          "Spec": {
            "DriverConfiguration": {},
            "IPAMOptions": {
              "Configs": [
                {
                  "Gateway": "10.255.0.1",
                  "Subnet": "10.255.0.0/16"
                }
              ],
              "Driver": {}
            },
            "Labels": {
              "com.docker.swarm.internal": "true"
            },
            "Name": "ingress"
          },
          "UpdatedAt": "2016-06-07T21:07:29.955277358Z",
          "Version": {
            "Index": 18
          }
        }
      }
    ],
    "NodeID": "60gvrl6tm78dmak4yl7srz94v",
    "ServiceID": "9mnpnzenvg8p8tdbtq4wvbkcz",
    "Slot": 1,
    "Spec": {
      "ContainerSpec": {
        "Image": "redis"
      },
      "Placement": {},
      "Resources": {
        "Limits": {},
        "Reservations": {}
      },
      "RestartPolicy": {
        "Condition": "any",
        "MaxAttempts": 0
      }
    },
    "Status": {
      "ContainerStatus": {
        "ContainerID": "e5d62702a1b48d01c3e02ca1e0212a250801fa8d67caca0b6f35919ebc12f035",
        "PID": 677
      },
      "Message": "started",
      "State": "running",
      "Timestamp": "2016-06-07T21:07:31.290032978Z"
    },
    "UpdatedAt": "2016-06-07T21:07:31.376370513Z",
    "Version": {
      "Index": 71
    }
  },
  {
    "CreatedAt": "2016-06-07T21:07:30.019104782Z",
    "DesiredState": "shutdown",
    "ID": "1yljwbmlr8er2waf8orvqpwms",
    "Name": "hopeful_cori",
    "NetworksAttachments": [
      {
        "Addresses": [
          "10.255.0.5/16"
        ],
        "Network": {
          "CreatedAt": "2016-06-07T20:31:11.912919752Z",
          "DriverState": {
            "Name": "overlay",
            "Options": {
              "com.docker.network.driver.overlay.vxlanid_list": "256"
            }
          },
          "ID": "4qvuz4ko70xaltuqbt8956gd1",
          "IPAMOptions": {
            "Configs": [
              {
                "Gateway": "10.255.0.1",
                "Subnet": "10.255.0.0/16"
              }
            ],
            "Driver": {
              "Name": "default"
            }
          },
          "Spec": {
            "DriverConfiguration": {},
            "IPAMOptions": {
              "Configs": [
                {
                  "Gateway": "10.255.0.1",
                  "Subnet": "10.255.0.0/16"
                }
              ],
              "Driver": {}
            },
            "Labels": {
              "com.docker.swarm.internal": "true"
            },
            "Name": "ingress"
          },
          "UpdatedAt": "2016-06-07T21:07:29.955277358Z",
          "Version": {
            "Index": 18
          }
        }
      }
    ],
    "NodeID": "60gvrl6tm78dmak4yl7srz94v",
    "ServiceID": "9mnpnzenvg8p8tdbtq4wvbkcz",
    "Slot": 1,
    "Spec": {
      "ContainerSpec": {
        "Image": "redis"
      },
      "Placement": {},
      "Resources": {
        "Limits": {},
        "Reservations": {}
      },
      "RestartPolicy": {
        "Condition": "any",
        "MaxAttempts": 0
      }
    },
    "Status": {
      "ContainerStatus": {
        "ContainerID": "1cf8d63d18e79668b0004a4be4c6ee58cddfad2dae29506d8781581d0688a213"
      },
      "Message": "shutdown",
      "State": "shutdown",
      "Timestamp": "2016-06-07T21:07:30.202183143Z"
    },
    "UpdatedAt": "2016-06-07T21:07:30.231958098Z",
    "Version": {
      "Index": 30
    }
  }
]
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | server error | [`Tasks500ErrorException`](../../doc/models/tasks-500-error-exception.md) |
| 503 | node is not part of a swarm | [`Tasks503ErrorException`](../../doc/models/tasks-503-error-exception.md) |


# Task Inspect

```php
function taskInspect(string $id): Task
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | ID of the task |

## Response Type

**200**: no error

[`Task`](../../doc/models/task.md)

## Example Usage

```php
$id = 'id0';

$taskController = $client->getTaskController();

try {
    $result = $taskController->taskInspect($id);
    echo 'Task:';
    var_dump($result);
} catch (Tasks404ErrorException $exp) {
    echo 'Caught Tasks404ErrorException:', $exp;
} catch (Tasks500ErrorException $exp) {
    echo 'Caught Tasks500ErrorException:', $exp;
} catch (Tasks503ErrorException $exp) {
    echo 'Caught Tasks503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | no such task | [`Tasks404ErrorException`](../../doc/models/tasks-404-error-exception.md) |
| 500 | server error | [`Tasks500ErrorException`](../../doc/models/tasks-500-error-exception.md) |
| 503 | node is not part of a swarm | [`Tasks503ErrorException`](../../doc/models/tasks-503-error-exception.md) |

