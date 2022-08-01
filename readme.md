![logo](https://raw.githubusercontent.com/SecureHats/SecureHacks/main/media/sh-banners.png)
=========
[![Maintenance](https://img.shields.io/maintenance/yes/2022.svg?style=flat-square)]()
# Microsoft Sentinel - Threat Intelligence Validator

This GitHub action can be used to validate Microsoft Sentinel file based threat intelligence files in both JSON and CSV format.
>Add the following code block to your Github workflow:

```yaml
name: TI
on: push

jobs:
  pester-test:
    name: validate threat intelligence
    runs-on: ubuntu-latest
    steps:
      - name: Check out repository code
        uses: actions/checkout@v3
      - name: Validate Sentinel Threat Intelligence
        uses: SecureHats/validate-detections@v1
        with:
          filesPath: threat-intel
          logLevel: Minimal
```

### Inputs

This Action defines the following formal inputs.

| Name | Req | Description
|-|-|-|
| **`filesPath`**  | false | Path to the directory that contain the files to be tested, relative to the root of the project. This path is optional and defaults to the project root, in which case all files across the entire project tree will be discovered.
| **`logLevel`** | false | This indicates the verbosity of the testing engine. The default is set to `Normal` which shows all the passed and failed tests in the output. Optional values are `None, Minimal, Normal, Detailed, Diagnostic` When using `Minimal` only non-passed test results will be shown. The available verbosity options are based on the [pester](https://pester-docs.netlify.app/docs/commands/Invoke-Pester#-show) documentation. 

## Current incuded tests

![image](https://user-images.githubusercontent.com/40334679/170026369-fa0fa7b8-e580-42d4-9c2d-c36edb506094.png)

## Current limitations / Under Development

- []
