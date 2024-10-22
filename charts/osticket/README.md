# OSTicket support ticket system Helm chart

This is a Helm chart to install OSTicket with MySQL as database and memcached as session storage.
 
Requirements:

 - Default persistent storage class (StorageClass)
 - Ingress Controller (ex: nginx)

## Parameters and default values

| Parametro                 | Description                                | Default                  |
|---------------------------|--------------------------------------------|--------------------------|
| image.repository          | Repository of docker image                 | `interlegis/osticket`    |
| image.tag                 | Docker image version                       | `1.14.1`                 |
| image.pullPolicy          | Docker image Pull Policy                   | `IfNotPresent`           |
| replicaCount              | Number of OSTicket replicas                | `1`                      |
| persistence.enabled       | Enable persistent volumes                  | `true`                   |
| persistence.storageClass  | Persistent volume storage class            | ``                       |
| persistence.accessMode    | Persistent volume acces mode               | `ReadWriteOnce`          |
| persistence.size          | Persistent volume size                     | `10Gi `                  |
| installSecret             | OSTicket install secret                    | ``                       |
| mariadb.auth.database     | OSTicket database name                     | `osticket`               |
| mariadb.auth.username     | OSTicket database user name                | `osticket`               |
| mariadb.auth.password     | OSTicket database user password            | `mysecretpw`             |
