# Node

Nodes are instances of the Engine participating in a swarm. Swarm mode must be enabled for these endpoints to work.

```php
$nodeController = $client->getNodeController();
```

## Class Name

`NodeController`

## Methods

* [Node List](../../doc/controllers/node.md#node-list)
* [Node Delete](../../doc/controllers/node.md#node-delete)
* [Node Inspect](../../doc/controllers/node.md#node-inspect)
* [Node Update](../../doc/controllers/node.md#node-update)


# Node List

```php
function nodeList(?string $filters = null): array
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `filters` | `?string` | Query, Optional | Filters to process on the nodes list, encoded as JSON (a `map[string][]string`).<br><br>Available filters:<br><br>- `id=<node id>`<br>- `label=<engine label>`<br>- `membership=`(`accepted`\|`pending`)`<br>- `name=<node name>`<br>- `role=`(`manager`\|`worker`)` |

## Response Type

**200**: no error

[`Node[]`](../../doc/models/node.md)

## Example Usage

```php
$nodeController = $client->getNodeController();

try {
    $result = $nodeController->nodeList();
    echo 'Node[]:';
    var_dump($result);
} catch (Nodes500ErrorException $exp) {
    echo 'Caught Nodes500ErrorException:', $exp;
} catch (Nodes503ErrorException $exp) {
    echo 'Caught Nodes503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 500 | server error | [`Nodes500ErrorException`](../../doc/models/nodes-500-error-exception.md) |
| 503 | node is not part of a swarm | [`Nodes503ErrorException`](../../doc/models/nodes-503-error-exception.md) |


# Node Delete

```php
function nodeDelete(string $id, ?bool $force = false): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID or name of the node |
| `force` | `?bool` | Query, Optional | Force remove a node from the swarm<br><br>**Default**: `false` |

## Response Type

**200**: no error

`void`

## Example Usage

```php
$id = 'id0';

$force = false;

$nodeController = $client->getNodeController();

try {
    $nodeController->nodeDelete(
        $id,
        $force
    );
} catch (Nodes404ErrorException $exp) {
    echo 'Caught Nodes404ErrorException:', $exp;
} catch (Nodes500ErrorException $exp) {
    echo 'Caught Nodes500ErrorException:', $exp;
} catch (Nodes503ErrorException $exp) {
    echo 'Caught Nodes503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | no such node | [`Nodes404ErrorException`](../../doc/models/nodes-404-error-exception.md) |
| 500 | server error | [`Nodes500ErrorException`](../../doc/models/nodes-500-error-exception.md) |
| 503 | node is not part of a swarm | [`Nodes503ErrorException`](../../doc/models/nodes-503-error-exception.md) |


# Node Inspect

```php
function nodeInspect(string $id): Node
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID or name of the node |

## Response Type

**200**: no error

[`Node`](../../doc/models/node.md)

## Example Usage

```php
$id = 'id0';

$nodeController = $client->getNodeController();

try {
    $result = $nodeController->nodeInspect($id);
    echo 'Node:';
    var_dump($result);
} catch (Nodes404ErrorException $exp) {
    echo 'Caught Nodes404ErrorException:', $exp;
} catch (Nodes500ErrorException $exp) {
    echo 'Caught Nodes500ErrorException:', $exp;
} catch (Nodes503ErrorException $exp) {
    echo 'Caught Nodes503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 404 | no such node | [`Nodes404ErrorException`](../../doc/models/nodes-404-error-exception.md) |
| 500 | server error | [`Nodes500ErrorException`](../../doc/models/nodes-500-error-exception.md) |
| 503 | node is not part of a swarm | [`Nodes503ErrorException`](../../doc/models/nodes-503-error-exception.md) |


# Node Update

```php
function nodeUpdate(string $id, int $version, ?NodeSpec $body = null): void
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `id` | `string` | Template, Required | The ID of the node |
| `version` | `int` | Query, Required | The version number of the node object being updated. This is required to avoid conflicting writes. |
| `body` | [`?NodeSpec`](../../doc/models/node-spec.md) | Body, Optional | - |

## Response Type

**200**: no error

`void`

## Example Usage

```php
$id = 'id0';

$version = 172;

$body = NodeSpecBuilder::init()
    ->availability(AvailabilityEnum::ACTIVE)
    ->labels(
        [
            'foo' => 'bar'
        ]
    )
    ->name('node-name')
    ->role(RoleEnum::MANAGER)
    ->build();

$nodeController = $client->getNodeController();

try {
    $nodeController->nodeUpdate(
        $id,
        $version,
        $body
    );
} catch (NodesUpdate400ErrorException $exp) {
    echo 'Caught NodesUpdate400ErrorException:', $exp;
} catch (NodesUpdate404ErrorException $exp) {
    echo 'Caught NodesUpdate404ErrorException:', $exp;
} catch (NodesUpdate500ErrorException $exp) {
    echo 'Caught NodesUpdate500ErrorException:', $exp;
} catch (NodesUpdate503ErrorException $exp) {
    echo 'Caught NodesUpdate503ErrorException:', $exp;
} catch (ApiException $exp) {
    echo 'Caught:', $exp;
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | bad parameter | [`NodesUpdate400ErrorException`](../../doc/models/nodes-update-400-error-exception.md) |
| 404 | no such node | [`NodesUpdate404ErrorException`](../../doc/models/nodes-update-404-error-exception.md) |
| 500 | server error | [`NodesUpdate500ErrorException`](../../doc/models/nodes-update-500-error-exception.md) |
| 503 | node is not part of a swarm | [`NodesUpdate503ErrorException`](../../doc/models/nodes-update-503-error-exception.md) |

