# Keepalived Helm Chart

This helm chart provides Keepalived as a DaemonSet for hosts with a specific nodeSelector (default role=ingress).

## Parameters and Default Values

| Parameter                    | Description                                | Default               |
| ---------------------------- | ------------------------------------------ | --------------------- |
| keepalived.auth_pass         | Keepalived authentication Password         | `agoodpwd`            |
| keepalived.check_port        | Port the service should be listening on    | `443                  |
| keepalived.check_script      | Custom script for service healthcheckabled | `ss -ltn | grep :443` |
| keepalived.interface         | Interface for keepalived heartbeats        | `eth0`                |
| keepalived.virtual_ip        | IP Address for your HA service             | `192.168.1.1 `        |
| keepalived.virtual_mask      | Network Mask for the HA IP Address         | `24`                  |
| keepalived.vrid              | VRRP Virtual Router ID (0-255)             | `124`                 |
| nodeSelector                 | Used to select the nodes for the daemonset | `role: ingress`       |
