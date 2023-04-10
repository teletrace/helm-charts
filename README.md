# Teletrace Helm Charts

This repository contains [Helm](https://helm.sh) charts for the [Teletrace](https://github.com/teletrace/teletrace) project.

## Usage

[Helm](https://helm.sh) must be installed to use the charts.
Please refer to Helm's [documentation](https://helm.sh/docs) to get started.

Once Helm has been set up correctly, add the repo as follows:

```sh
helm repo add teletrace https://teletrace.github.io/helm-charts/
```

If you had already added this repo earlier, run `helm repo update` to retrieve
the latest versions of the packages.\
You can then run `helm search repo teletrace` to see the charts.
