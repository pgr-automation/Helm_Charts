# Helm_Charts
# Helm Commands with Usages

Helm is a Kubernetes package manager used to manage charts and releases. This document provides a comprehensive list of Helm commands with their usages.

---

## General Commands

### `helm version`
- **Description**: Displays the Helm client and server versions.
- **Usage**:
  ```bash
  helm version
  ```

### `helm help`
- **Description**: Displays help for Helm commands.
- **Usage**:
  ```bash
  helm help
  ```

---

## Repository Management

### `helm repo add`
- **Description**: Adds a new Helm chart repository.
- **Usage**:
  ```bash
  helm repo add <name> <url>
  ```
  Example:
  ```bash
  helm repo add stable https://charts.helm.sh/stable
  ```

### `helm repo update`
- **Description**: Updates the local cache of chart repositories.
- **Usage**:
  ```bash
  helm repo update
  ```

### `helm repo list`
- **Description**: Lists all chart repositories configured locally.
- **Usage**:
  ```bash
  helm repo list
  ```

### `helm repo remove`
- **Description**: Removes a chart repository.
- **Usage**:
  ```bash
  helm repo remove <name>
  ```

---

## Searching

### `helm search hub`
- **Description**: Searches for charts in the Helm Hub.
- **Usage**:
  ```bash
  helm search hub <keyword>
  ```

### `helm search repo`
- **Description**: Searches for charts in configured repositories.
- **Usage**:
  ```bash
  helm search repo <keyword>
  ```

---

## Chart Management

### `helm install`
- **Description**: Installs a Helm chart.
- **Usage**:
  ```bash
  helm install <release-name> <chart-name> [flags]
  ```
  Example:
  ```bash
  helm install my-release stable/nginx
  ```

### `helm upgrade`
- **Description**: Upgrades a release to a new chart version.
- **Usage**:
  ```bash
  helm upgrade <release-name> <chart-name> [flags]
  ```
  Example:
  ```bash
  helm upgrade my-release stable/nginx
  ```

### `helm uninstall`
- **Description**: Uninstalls a release from the cluster.
- **Usage**:
  ```bash
  helm uninstall <release-name>
  ```
  Example:
  ```bash
  helm uninstall my-release
  ```

### `helm list`
- **Description**: Lists all releases in the current namespace.
- **Usage**:
  ```bash
  helm list
  ```

### `helm rollback`
- **Description**: Rolls back a release to a previous version.
- **Usage**:
  ```bash
  helm rollback <release-name> <revision>
  ```
  Example:
  ```bash
  helm rollback my-release 1
  ```

### `helm history`
- **Description**: Displays the history of a release.
- **Usage**:
  ```bash
  helm history <release-name>
  ```

### `helm status`
- **Description**: Displays the status of a release.
- **Usage**:
  ```bash
  helm status <release-name>
  ```

### `helm show`
- **Description**: Shows information about a chart.
- **Subcommands**:
  - `helm show chart <chart>`: Displays chart metadata.
  - `helm show values <chart>`: Displays default values.
  - `helm show all <chart>`: Displays all details.
- **Usage**:
  ```bash
  helm show values stable/nginx
  ```

---

## Chart Development

### `helm create`
- **Description**: Creates a new chart.
- **Usage**:
  ```bash
  helm create <chart-name>
  ```
  Example:
  ```bash
  helm create mychart
  ```

### `helm package`
- **Description**: Packages a chart directory into a `.tgz` file.
- **Usage**:
  ```bash
  helm package <chart-directory>
  ```

### `helm lint`
- **Description**: Validates a chart for syntax or logical errors.
- **Usage**:
  ```bash
  helm lint <chart-directory>
  ```

### `helm dependency`
- **Description**: Manages chart dependencies.
- **Subcommands**:
  - `helm dependency update`: Updates dependencies in `Chart.yaml`.
  - `helm dependency list`: Lists dependencies for a chart.
- **Usage**:
  ```bash
  helm dependency update <chart-directory>
  ```

---

## Template Rendering

### `helm template`
- **Description**: Generates Kubernetes manifests from a chart without installing it.
- **Usage**:
  ```bash
  helm template <release-name> <chart-name>
  ```

---

## Debugging

### `helm get`
- **Description**: Fetches details of a release.
- **Subcommands**:
  - `helm get values`: Gets the values of a release.
  - `helm get manifest`: Fetches the Kubernetes manifests.
  - `helm get hooks`: Fetches release hooks.
- **Usage**:
  ```bash
  helm get values my-release
  ```

### `helm test`
- **Description**: Runs tests for a release.
- **Usage**:
  ```bash
  helm test <release-name>
  ```

### `helm debug`
- **Description**: Enables verbose output for troubleshooting.
- **Usage**:
  ```bash
  helm install <release-name> <chart-name> --debug --dry-run
  ```

---

## Others

### `helm upgrade --install`
- **Description**: Upgrades a release if it exists or installs it otherwise.
- **Usage**:
  ```bash
  helm upgrade --install <release-name> <chart-name>
  ```

### `helm diff` (Requires the Helm Diff plugin)
- **Description**: Shows the difference between two releases or a release and a chart.
- **Usage**:
  ```bash
  helm diff upgrade <release-name> <chart-name>
  ```

### `helm plugin`
- **Description**: Manages Helm plugins.
- **Subcommands**:
  - `helm plugin install <url>`: Installs a plugin.
  - `helm plugin list`: Lists installed plugins.
- **Usage**:
  ```bash
  helm plugin list
  ```

---

Let me know if further details are needed for any specific command!
