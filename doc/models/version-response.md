
# Version Response

## Structure

`VersionResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `apiVersion` | `?string` | Optional | - | getApiVersion(): ?string | setApiVersion(?string apiVersion): void |
| `arch` | `?string` | Optional | - | getArch(): ?string | setArch(?string arch): void |
| `buildTime` | `?string` | Optional | - | getBuildTime(): ?string | setBuildTime(?string buildTime): void |
| `experimental` | `?bool` | Optional | - | getExperimental(): ?bool | setExperimental(?bool experimental): void |
| `gitCommit` | `?string` | Optional | - | getGitCommit(): ?string | setGitCommit(?string gitCommit): void |
| `goVersion` | `?string` | Optional | - | getGoVersion(): ?string | setGoVersion(?string goVersion): void |
| `kernelVersion` | `?string` | Optional | - | getKernelVersion(): ?string | setKernelVersion(?string kernelVersion): void |
| `minAPIVersion` | `?string` | Optional | - | getMinAPIVersion(): ?string | setMinAPIVersion(?string minAPIVersion): void |
| `os` | `?string` | Optional | - | getOs(): ?string | setOs(?string os): void |
| `version` | `?string` | Optional | - | getVersion(): ?string | setVersion(?string version): void |

## Example

```php
use DockerLib\Models\Builders\VersionResponseBuilder;

$versionResponse = VersionResponseBuilder::init()
    ->apiVersion('ApiVersion6')
    ->arch('Arch8')
    ->buildTime('BuildTime8')
    ->experimental(false)
    ->gitCommit('GitCommit0')
    ->build();
```

