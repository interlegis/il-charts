# Local Path Provisioner Helm Chart

## Overview

The Local Path Provisioner provides a way for the Kubernetes users to utilize the local storage in each node. Based on the user configuration, the Local Path Provisioner will create hostPath based persistent volume on the node automatically. It utilizes the features introduced by Kubernetes Local Persistent Volume feature, but make it a simpler solution than the built-in local volume feature in Kubernetes.

This is a Local Path Provisioner Helm chart based on the chart of Kubernetes Incubator local-volume-provisioner.

See https://github.com/rancher/local-path-provisioner for more information.

## Configurations

The following table lists the configurable parameters of the local path provisioner chart and their default values.

| Parameter                  | Description                                                                                           | Type     | Default                                  |
| ---                        | ---                                                                                                   | ---      | ---                                      |
| common.rbac                | Generating RBAC (Role Based Access Control) objects.                                                  | bool     | `true`                                   |
| common.namespace           | Namespace where provisioner runs.                                                                     | str      | `default`                                |
| common.createNamespace     | Whether to create namespace for provisioner.                                                          | bool     | `false`                                  |
| common.configMapName       | Provisioner ConfigMap name.                                                                           | str      | `local-provisioner-config`               |
| class.name                 | StorageClass name.                                                                                    | str      | `local-path`                             |
| class.hostDir              | Path on the host where local volumes of this storage class are mounted under.                         | str      | `/opt/local-path-provisioner`            |
| class.storageClass         | Create storage class for this class and configure it optionally.                                      | bool/map | `true`                                   |
| class.reclaimPolicy        | Specify reclaimPolicy of storage class, available: Delete/Retain.                                     | str      | `Delete`                                 |
| deployment.name            | Provisioner DaemonSet name.                                                                           | str      | `local-path-provisioner`                 |
| deployment.image           | Provisioner image.                                                                                    | str      | `rancher/local-path-provisioner:v0.0.2`  |
| deployment.imagePullPolicy | Provisioner DaemonSet image pull policy.                                                              | str      | `Always`                                 |
| deployment.serviceAccount  | Provisioner DaemonSet service account.                                                                | str      | `local-path-provisioner-service-account` |
| deployment.nodeSelector    | NodeSelector constraint on nodes eligible to run the provisioner.                                     | map      | `-`                                      |
| deployment.tolerations     | List of tolerations to be applied to the Provisioner DaemonSet.                                       | list     | `-`                                      |
| deployment.resources       | Map of resource request and limits to be applied to the Provisioner Daemonset.                        | map      | `-`                                      | 
