# Helm chart para Portal Modelo

Este é um Helm Chart para instalação de um Portal Modelo para Casas Legislativas em uma infraestrutura Kubernetes. Requisitos:

 - Classe de armazenamento persistente (StorageClass)
 - Provisionador automático de volumes (ex: nfs-provisioner)
 - Ingress Controller (ex: nginx)

## Parametros e valores padrão

| Parametro                 | Description                                | Default                  |
|---------------------------|--------------------------------------------|--------------------------|
| image.repository          | Repositorio da imagem Docker               | `interlegis/portalmodelo`|
| image.tag                 | Versão da imagem Docker                    | `3.0-17`                 |
| image.pullPolicy          | Política de baixar nova imagem             | `IfNotPresent`           |
| replicaCount              | Numero de instâncias do Plone              | `1`                      |
| persistence.enabled       | Habilita o uso de volumes persistentes     | `true`                   |
| persistence.storageClass  | Classe de armazenamento dos volumes        | `managed-nfs-storage`    |
| persistence.accessMode    | Modo de acesso do volume                   | `ReadWriteOnce`          |
| persistence.size          | Tamanho do volume provisionado             | `100Mi`                  |
| portal.adminPassword      | Senha de Administrador inicial do portal   | `altereme`               |
| portal.adminEmail         | E-mail do administrador do portal          | `contato@tecnico.net`    |
| portal.title              | Título na página inicial do portal         | `Câmara Municipal`       |
| portal.description        | Descrição abaixo do título do portal       | `Cidade - UF`            |
| portal.hostname           | Nome de domínio utilizado para acessá-lo   | `teste.df.leg.br`        |
| instance.zeoclient        | Se o Portal rodará com Zeoserver ou sem    | `false` (sem zeo)        |
| ingress.enabled           | Habilita um Ingress para o Portal          | `true`                   |
| ingress.annotations       | Annotations para o Ingress Controller      | `{}`                     |
