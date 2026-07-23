
# Registry Service Config Index Configs

## Data Type

`array|null|IndexInfo`

## Cases

| Type |
|  --- |
| `?array` |
| [`IndexInfo`](../../../doc/models/index-info.md) |

## ?array

### Initialization Code

#### Example

```php
$value = ApiHelper::deserialize('{"key1":"val1","key2":"val2"}');
```

## IndexInfo

### Initialization Code

#### Example

```php
$value = IndexInfoBuilder::init()
    ->mirrors(
        [
            'https://hub-mirror.corp.example.com:5000/',
            'https://registry-2.docker.io/',
            'https://registry-3.docker.io/'
        ]
    )
    ->name('docker.io')
    ->official(true)
    ->secure(true)
    ->build();
```

