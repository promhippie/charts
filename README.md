# Charts

[![Release Build](https://github.com/promhippie/charts/workflows/release.yml/badge.svg)](https://github.com/promhippie/charts/actions/workflows/release.yaml) [![Join the Matrix chat at https://matrix.to/#/#webhippie:matrix.org](https://img.shields.io/badge/matrix-%23webhippie-7bc9a4.svg)](https://matrix.to/#/#webhippie:matrix.org) [![Artifact Hub](https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/promhippie)](https://artifacthub.io/packages/search?repo=promhippie)

Definition and publishing of Helm charts to install all the tools built within
the Promhippie GitHub organization.

## Usage

Make sure you have install [Helm][helm], after that you can install the charts
repository and search for available charts:

```console
helm repo add promhippie https://promhippie.github.io/charts
helm search repo promhippie
```

## Security

If you find a security issue please contact
[thomas@webhippie.de](mailto:thomas@webhippie.de) first.

## Contributing

Fork -> Patch -> Push -> Pull Request

## Authors

-   [Thomas Boerger](https://github.com/tboerger)

## License

Apache-2.0

## Copyright

```console
Copyright (c) 2021 Thomas Boerger <thomas@webhippie.de>
```

[helm]: https://helm.sh
