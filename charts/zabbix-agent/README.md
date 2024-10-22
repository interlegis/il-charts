# Zabbix Agent Helm Chart

This helm chart provides Zabbix Agent as a DaemonSet for all your Kubernetes hosts.

## Default Values

The configuration parameters in this section control the resources requested and utilized by the Apache SOLR Cloud Instance.

| Parameter                   | Description                                       | Default     |
| --------------------------- | --------------------------------------------------| ----------- |
| zabbix.serverHost           | IP Address of your Zabbix Server or Zabbix Proxy  | `localhost` |
| zabbix.debugLevel           | Debug information level                           | `3`         |
| zabbix.enableRemoteCommands | If remote execution is enabled or disabled        | `0`         |
| zabbix.refreshActiveChecks  | Seconds to refresh Active Checks                  | `120`       |
| zabbix.startAgents          | Number of agent threads to start                  | `10`        |
| zabbix.timeout              | Timeout for each item in seconds                  | `30`        |
