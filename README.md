# Platform Dummy Template Repository

This repository contains a few dummy templates for VeeCode Platform DevPortal.

These serve as examples of our standard "Environment" --> "Cluster" --> "Project" hierarchy and also as a starting point to implement new templates of your own design from scratch.


## Templates

The repository includes the following templates:

- `environment`: An example of an environment template implementation.
- `project`: An example of a project template implementation.
- `cluster`: An example of a cluster template implementation.

## Usage

To use these templates, clone this repository and configure it in your devportal catalog.

## Development

A quick way to run DevPortal loading this repository as a template library can de done using [Okteto](https://okteto.com/).

```bash
okteto context use https://cloud.okteto.com # okteto login
okteto kubeconfigexport NAMESPACE="your-okteto-namespace"
helm upgrade devportal --install veecode-platform/devportal \
  --set "platform.behaviour.mode=demo" \
  --set "appConfig.app.baseUrl=https://devportal-${NAMESPACE}.cloud.okteto.net" \
  --set "appConfig.backend.baseUrl=https://devportal-${NAMESPACE}.cloud.okteto.net"  \
  --set "locations[0].type=url,locations[0].target=https://github.com/veecode-platform/dummy-catalog/blob/main/catalog-info.yaml"
```

A read-only DevPortal instance will be available at `https://devportal-${NAMESPACE}.cloud.okteto.net`.

## Documentation

For more information about using these templates and configuring them in your devportal catalog, please refer to the [Platform Documentation](https://docs.platform.vee.codes/).