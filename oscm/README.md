# Helm chart for Open Services Catalog Manager

Open Services Catalog Manager (OSCM) provides an asynchronous platform for provisioning services on your cloud infrastructure. It offers ready-to-use service provisioning adapters for IaaS providers like Amazon Web Services (AWS), OpenStack and Kubernetes, but is also open for integrating other platforms.

Service Providers can define their services with flexible price models and publish them to an OSCM Marketplace. The Service Provider can decide on using the OSCM Billing Engine for the service usage cost calculation, or integrate an external one. Customers can subscribe to and use the services.

Find more details on the OSCM homepage [https://openservicecatalogmanager.org/ui].

## Configuration options and Default Values

| Parameter                 | Description                               | Default                   |
|---------------------------|-------------------------------------------|---------------------------|
| image.repository          | OSCM Core Image repository                | `servicecatalog/oscm-core`|
| image.tag                 | OSCM Core Image tag                       | `latest`                  |
| image.pullPolicy          | OSCM Core Image Pull Policy               | `IfNotPresent`            |
| initdb.repository         | OSCM InitDB Image repository              | `servicecatalog/oscm-core`|
| initdb.tag                | OSCM InitDB Image tag                     | `latest`                  |
| initdb.pullPolicy         | OSCM InitDB Image Pull Policy             | `IfNotPresent`            |
| replicaCount              | Number of OSCM Replicas                   | `1`                       |
| service.type              | Kubernetes Service Type                   | `ClusterIP`               |
| service.port              | Kubernetes Service Port                   | `8080`                    |
| provisioning.kubernetes   | Whether to install K8S provisioning       | `false`                   |
| ingress.enabled           | Whether to enable Ingress                 | `true`                    |
| ingress.annotations       | Annotations for the Ingress Controller    | `{}`                      |
| ingress.path              | Path on the backend for the Ingress       | `/`                       |
| ingress.hostname          | Ingress hostname                          | `localhost`               |
| ingress.tls               | Whether to enable TLS for Ingress         | `false`                   |
| smtp.host                 | SMTP host to send mail messages           | `localhost`               |
| smtp.port                 | SMTP port to send mail messages           | `25`                      |
| smtp.from                 | SMTP mail from address                    | `oscm@localhost`          |
| smtp.user                 | Username for SMTP authentication          | ``                        |
| smtp.password             | Password for SMTP authentication          | ``                        |
| smtp.auth                 | Whether to enable SMTP authentication     | `false`                   |
| smtp.tls                  | Whether to use TLS for SMTP connections   | `true`                    |
| postgresql                | Options as defined in Postgresql chart    | see values.yaml           |
| resources                 | Resources definition, defined by the user | {}                        |
| tolerations               | Tolerations definitions                   | {}                        |
