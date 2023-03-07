# Helm charts

This directory contains Helm charts for Grafana Agent.

## Testing

The `tests` contains a list of golden templates rendered from the Helm chart.

These manifests are never run directly, but are instead used to validate the
correctness of the templates emitted by the Helm chart. To regenerate this
folder, call `make generate-helm-tests` from the root of the repository.

`make generate-helm-tests` will iterate through the value.yaml files in
`charts/grafana-agent/tests` and generate each one as a separate directory.

When modifying the Helm charts, `make generate-helm-tests` must be run before
submitting a PR, as a linter check will ensure that this directory is up to
date.

## Usage

[Helm](https://helm.sh) must be installed to use the charts.
Please refer to Helm's [documentation](https://helm.sh/docs/) to get started.

Once Helm is set up properly, add the repo as follows:

```console
helm repo add grafana-agent-hw https://healthwise.github.io/grafana-agent-helm-chart
```

You can then run `helm search repo grafana-agent-hw` to see the charts.