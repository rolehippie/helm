# helm

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&amp;logoColor=white)](https://github.com/rolehippie/helm)
[![General Workflow](https://github.com/rolehippie/helm/actions/workflows/general.yml/badge.svg)](https://github.com/rolehippie/helm/actions/workflows/general.yml)
[![Readme Workflow](https://github.com/rolehippie/helm/actions/workflows/readme.yml/badge.svg)](https://github.com/rolehippie/helm/actions/workflows/readme.yml)
[![Galaxy Workflow](https://github.com/rolehippie/helm/actions/workflows/galaxy.yml/badge.svg)](https://github.com/rolehippie/helm/actions/workflows/galaxy.yml)
[![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/helm)](https://github.com/rolehippie/helm/blob/master/LICENSE)
[![Ansible Role](https://img.shields.io/badge/role-rolehippie.helm-blue)](https://galaxy.ansible.com/rolehippie/helm)

Ansible role to install helm package manager for kubernetes.

## Sponsor

Building and improving this Ansible role have been sponsored by my current and previous employers like **[Cloudpunks GmbH](https://cloudpunks.de)** and **[Proact Deutschland GmbH](https://www.proact.eu)**.

## Table of content

- [Requirements](#requirements)
- [Default Variables](#default-variables)
  - [helm_core_arch](#helm_core_arch)
  - [helm_core_download](#helm_core_download)
  - [helm_core_version](#helm_core_version)
  - [helm_docs_arch](#helm_docs_arch)
  - [helm_docs_download](#helm_docs_download)
  - [helm_docs_enabled](#helm_docs_enabled)
  - [helm_docs_version](#helm_docs_version)
  - [helm_install_path](#helm_install_path)
  - [helm_test_arch](#helm_test_arch)
  - [helm_test_download](#helm_test_download)
  - [helm_test_enabled](#helm_test_enabled)
  - [helm_test_version](#helm_test_version)
- [Discovered Tags](#discovered-tags)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Requirements

- Minimum Ansible version: `2.10`


## Default Variables

### helm_core_arch

Architecture for helm binary

#### Default value

```YAML
helm_core_arch: "{{ 'arm64' if ansible_architecture == 'aarch64' else 'amd64' }}"
```

### helm_core_download

URL to download helm binary from

#### Default value

```YAML
helm_core_download: https://get.helm.sh/helm-v{{ helm_core_version }}-linux-{{ helm_core_arch
  }}.tar.gz
```

### helm_core_version

Version of helm binary to install

#### Default value

```YAML
helm_core_version: 3.12.3
```

### helm_docs_arch

Architecture for helm docs

#### Default value

```YAML
helm_docs_arch: "{{ 'arm64' if ansible_architecture == 'aarch64' else 'x86_64' }}"
```

### helm_docs_download

URL to download helm docs from

#### Default value

```YAML
helm_docs_download: https://github.com/norwoodj/helm-docs/releases/download/v{{ helm_docs_version
  }}/helm-docs_{{ helm_docs_version }}_Linux_{{ helm_docs_arch }}.tar.gz
```

### helm_docs_enabled

Enable installation of helm docs

#### Default value

```YAML
helm_docs_enabled: true
```

### helm_docs_version

Version of helm docs to install

#### Default value

```YAML
helm_docs_version: 1.11.0
```

### helm_install_path

Path to install the binaries

#### Default value

```YAML
helm_install_path: /usr/bin
```

### helm_test_arch

Architecture for helm test

#### Default value

```YAML
helm_test_arch: "{{ 'arm64' if ansible_architecture == 'aarch64' else 'amd64' }}"
```

### helm_test_download

URL to download helm test from

#### Default value

```YAML
helm_test_download: https://github.com/helm/chart-testing/releases/download/v{{ helm_test_version
  }}/chart-testing_{{ helm_test_version }}_linux_{{ helm_test_arch }}.tar.gz
```

### helm_test_enabled

Enable installation of helm test

#### Default value

```YAML
helm_test_enabled: true
```

### helm_test_version

Version of helm test to install

#### Default value

```YAML
helm_test_version: 3.9.0
```

## Discovered Tags

**_helm_**


## Dependencies

- None

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
