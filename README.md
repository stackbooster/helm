# Stackbooster Helm Charts

Welcome to the Helm charts repository by **Stackbooster**.

## Repository Contents

- **charts/**
  - `stackbooster-agent` last version `1.0.1` — the Helm chart package for installing the agent.

## How to Add the Repository

To add this repository to your local Helm configuration, run:

```
helm repo add stackbooster https://raw.githubusercontent.com/stackbooster/helm/main/charts
helm repo update
```

After that, Helm will be able to find the `stackbooster-agent` chart in the `stackbooster` repository.

## Installing the Chart

To install the chart named `stackbooster-agent`, run:

```
helm install <releaseName> stackbooster/stackbooster-agent --version 1.0.1
```

If needed, you can specify the desired agent mode (`agentMode`) via the `--set` parameter. For example:

- **Full mode** (`full`):
  ```
  helm install stackbooster stackbooster/stackbooster-agent --version 1.0.1 --set agentMode=full --namespace stackbooster —create-namespace
  ```
- **Minimal mode** (`readonly`):
  ```
  helm install stackbooster stackbooster/stackbooster-agent --version 1.0.1 --set agentMode=readonly --namespace stackbooster —create-namespace
  ```

> **Important**: When using `agentMode=full`, the chart requires [cert-manager](https://cert-manager.io) to be installed in the cluster.  
> If `cert-manager` is not found during installation, the process will fail with a clear error message.  
> You can install cert-manager by following the official instructions here:  
> 👉 https://cert-manager.io/docs/installation/helm/

## Upgrading the Chart

If you have already installed the chart and want to change the mode (or any other parameters), use the `helm upgrade` command.  
For example, to switch to full mode:

```
helm upgrade stackbooster stackbooster/stackbooster-agent --version 1.0.1 --set agentMode=full --namespace stackbooster
```

## Verifying Chart Availability

To verify the chart is available in the repository, run:

```
helm search repo stackbooster
```

You can also search by name, for example:

```
helm search repo stackbooster-agent
```

## Additional Information

- [Official Helm Documentation](https://helm.sh/docs/)
- [Details on installing and managing charts using Helm](https://helm.sh/docs/intro/quickstart/)

If you have any questions, feel free to open an Issue or create a Pull Request in this repository.