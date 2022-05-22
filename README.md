# helm-repo-test

## Overview 

A repo to host a helm charts repo for testing helm apps like [helm-chartmap](https://github.com/melahn/helm-chartmap) and [helm-chartmap-generator](https://github.com/melahn/helm-chartmap-generator).

## Usage

Add this to your helm repo list, like this ...

```
helm repo add my-test-repo https://melahn.github.io/helm-repo-test
```

Then you can get any of the charts in the repo using helm commands.

## Design

There are five helm charts in this repo, each with a different characteristic to allow testing variations in test tools.

- test-app-a 
  - version 0.1.0
- test-app-b 
  - version 0.1.0
  - version 0.2.0
- test-app-c
  - version 0.1.0
  - version 0.2.0
  - version 0.3.0
- test-app-d
  - version 0.1.0
    - test-app-e 
      - version 0.1.0
        - test-app-f
          - version 0.1.0
          - depends on https://melahn.github.io/helm-repo test-app-x
- test-app-d
  - version 0.2.0
    - test-app-e 
      - version 0.1.0
        - test-app-f
          - version 0.1.0
          - depends on https://melahn.github.io/helm-repo test-app-x
- test-app-g
  - version 0.1.0
    - test-app-h 
      - version 0.1.0
        - test-app-i
          - version 0.1.0
          - depends on https://melahn.github.io/helm-repo no-chart-here (the chart does not exist)

## Build

The repo is entirely build from scratch by running the [GitHub Build Action](https://github.com/melahn/helm-repo-test/blob/main/.github/workflows/create-helm-repo.yml)




