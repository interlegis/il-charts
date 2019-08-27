# OSTicket support ticket system Helm chart

This is a Helm chart to install OSTicket with MySQL as database and memcached as session storage. 
Requirements:

 - Default persistent storage class (StorageClass)
 - Ingress Controller (ex: nginx)

## Parameters and default values

| Parametro                 | Description                                | Default                  |
|---------------------------|--------------------------------------------|--------------------------|
| image.repository          | Repository of docker image                 | `interlegis/osticket`    |
| image.tag                 | Docker image version                       | `1.12.2`                 |
| image.pullPolicy          | Docker image Pull Policy                   | `IfNotPresent`           |
| replicaCount              | Number of OSTicket replicas                | `1`                      |
| persistence.enabled       | Enable persistent volumes                  | `true`                   |
| persistence.storageClass  | Persistent volume storage class            | ``                       |
| persistence.accessMode    | Persistent volume acces mode               | `ReadWriteOnce`          |
| persistence.size          | Persistent volume size                     | `10Gi `                  |
| installSecret             | OSTicket install secret                    | ``                       |
| mysql.mysqlDatabase       | OSTicket database name                     | `osticket`               |
| mysql.mysqlUser           | OSTicket database user name                | `osticket`               |
| mysql.mysqlPassword       | OSTicket database user password            | `mysecretpw`             |
