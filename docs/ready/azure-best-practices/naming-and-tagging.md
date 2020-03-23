---
title: Convenciones recomendadas de nomenclatura y etiquetado
description: Conozca recomendaciones detalladas sobre nomenclatura y etiquetado de recursos diseñadas específicamente para apoyar los esfuerzos de adopción de la nube en la empresa.
author: BrianBlanchard
ms.author: brblanch
ms.date: 03/05/2020
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: ready
ms.custom: readiness, fasttrack-edit
ms.openlocfilehash: 119a0b64fe81e593404735e5ce6bc0c656ab23e2
ms.sourcegitcommit: 5411c3b64af966b5c56669a182d6425e226fd4f6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2020
ms.locfileid: "79312747"
---
<!-- cSpell:ignore eastus westus westeurope usgovia accountlookup messagequery -->

# <a name="recommended-naming-and-tagging-conventions"></a>Convenciones recomendadas de nomenclatura y etiquetado

Organice sus recursos en la nube para dar apoyo a los requisitos de administración de operaciones y de contabilidad. Unas convenciones de nomenclatura y etiquetado de metadatos bien definidas ayudan a localizar y administrar los recursos rápidamente. Estas convenciones también ayudan a asociar los costos de uso de la nube a los equipos empresariales mediante los mecanismos de contabilidad de contracargo y visualización de costos.

En la guía de [nomenclatura y restricciones de nombres de recursos de Azure](https://docs.microsoft.com/azure/architecture/best-practices/resource-naming) del Centro de arquitectura de Azure se proporcionan recomendaciones generales y las limitaciones de plataforma. El siguiente análisis amplía esa guía con recomendaciones más detalladas dirigidas específicamente a respaldar las labores de adopción de la nube empresarial.

El cambio de nombres de los recursos puede ser difícil. Establezca una convención de nomenclatura completa antes de comenzar cualquier implementación de nube de gran tamaño.

> [!NOTE]
> Cada empresa tiene diferentes requisitos de organización y administración. Estas recomendaciones sirven como punto de partida para los análisis dentro de los equipos de adopción de la nube.
>
> A medida que estos análisis avanzan, use la siguiente plantilla para capturar las decisiones sobre nomenclatura y etiquetado que tome al alinear estas recomendaciones con sus necesidades empresariales específicas.
>
> Descargue la [plantilla de seguimiento de convención de nomenclatura y etiquetado](https://archcenter.blob.core.windows.net/cdn/fusion/readiness/CAF%20Readiness%20Naming%20and%20Tagging%20tracking%20template.xlsx).

## <a name="naming-and-tagging-resources"></a>Nomenclatura y etiquetado de recursos

Una estrategia de nomenclatura y etiquetado incluye detalles empresariales y operativos como componentes de nombres de recursos y etiquetas de metadatos:

- La parte empresarial de esta estrategia garantiza que los nombres y las etiquetas de los recursos incluyen la información organizativa necesaria para identificar a los equipos. Use un recurso junto con los propietarios de la empresa responsables de los costos de los recursos.
- El lado operativo garantiza que los nombres y las etiquetas incluyen información que los equipos de TI usan para identificar la carga de trabajo, la aplicación, el entorno, la importancia y otra información útil para administrar los recursos.

## <a name="resource-naming"></a>Nombres de recursos

Una convención de nomenclatura efectiva ensambla los nombres de recursos usando información importante del recursos como parte de su nombre. Por ejemplo, mediante las [convenciones de nomenclatura recomendadas](#example-names), un recurso de IP pública para una carga de trabajo de producción de SharePoint se denomina así: `pip-sharepoint-prod-westus-001`.

A partir del nombre, puede identificar rápidamente el tipo del recurso, su carga de trabajo asociada, su entorno de implementación y la región de Azure que lo hospeda.

### <a name="naming-scope"></a>Ámbito de nomenclatura

Todos los tipos de recursos de Azure tienen un ámbito que define el nivel en el que los nombres de los recursos deben ser únicos. Un recurso debe tener un nombre único dentro de su ámbito.

Por ejemplo, una red virtual tiene un ámbito de grupo de recursos, lo que significa que solo puede haber una red llamada `vnet-prod-westus-001` en un grupo de recursos determinado. Otros grupos de recursos pueden tener su propia red virtual llamada `vnet-prod-westus-001`. Las subredes, para proporcionar otro ejemplo, tienen como ámbito las redes virtuales, lo que significa que cada subred de una red virtual debe tener un nombre único.

Algunos nombres de recursos, como los servicios PaaS con puntos de conexión públicos o etiquetas DNS de máquina virtual, tienen ámbitos globales, lo que significa que deben ser únicos en toda la plataforma de Azure.

Los nombres de los recursos tienen límites de longitud. Equilibrar el contexto insertado en un nombre con su ámbito y longitud es importante al desarrollar las convenciones de nomenclatura. Para más información sobre las reglas de nomenclatura de los caracteres, los ámbitos y las longitudes de nombres permitidos para los tipos de recursos, consulte [Convenciones de nomenclatura para los recursos de Azure](https://docs.microsoft.com/azure/architecture/best-practices/resource-naming).

### <a name="recommended-naming-components"></a>Componentes de nomenclatura recomendados

Cuando construya su convención de nomenclatura, identifique las partes clave de la información que quiere reflejar en el nombre de un recurso. Cada información es pertinente para un tipo de recurso. En la lista siguiente se proporcionan ejemplos de información que son útiles al construir nombres de recursos.

Mantenga corta la longitud de los componentes de nomenclatura para evitar que se superen los límites de longitud de los nombres de recursos.

| Componente de nomenclatura            | Descripción                                                                                                                                                                                                      | Ejemplos                                         |
|-----------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|
| Unidad de negocio               | División de nivel superior de la empresa que posee la suscripción o la carga de trabajo a la que pertenece el recurso. En organizaciones más pequeñas, este componente podría representar un único elemento organizativo de nivel superior corporativo. | _fin_, _mktg_, _product_, _it_, _corp_           |
| Tipo de suscripción           | Descripción resumida del propósito de la suscripción que contiene el recurso. A menudo desglosado por tipo de entorno de implementación o cargas de trabajo específicas.                                                       | _prod_, _shared_, _client_                       |
| Nombre de aplicación o servicio | Nombre de la aplicación, carga de trabajo o servicio del que forma parte el recurso.                                                                                                                                    | _navigator_, _emissions_, _sharepoint_, _hadoop_ |
| Entorno de implementación      | Fase del ciclo de vida de desarrollo de la carga de trabajo que admite el recurso.                                                                                                                              | _prod_, _dev_, _qa_, _stage_, _test_             |
| Region                      | La región de Azure en la que se implementa el recurso.                                                                                                                                                                 | _westus_, _eastus2_, _westeurope_, _usgovia_     |

### <a name="recommended-resource-type-prefixes"></a>Prefijos de tipo de recurso recomendados

Cada carga de trabajo puede constar de muchos recursos y servicios individuales. La incorporación de prefijos de tipo de recurso a los nombres de recursos facilita la identificación visual de los componentes de aplicaciones o servicios.

En la lista siguiente se proporcionan los prefijos de tipo de recurso de Azure recomendados que se deben usar al definir las convenciones de nomenclatura.

<!-- cSpell:disable -->

### <a name="general"></a>General

| Tipo de recurso                      | Prefijo de nombre |
|---------------------------------|-------------|
| Resource group                  | rg-         |
| Definición de directiva               | policy-     |
| Instancia del servicio API Management | apim-       |

### <a name="networking"></a>Redes

| Tipo de recurso                       | Prefijo de nombre |
|----------------------------------|-------------|
| Virtual network                  | vnet-       |
| Subnet                           | snet-       |
| Tarjeta de interfaz de red (NIC)          | nic-        |
| Dirección IP pública                | pip-        |
| Equilibrador de carga (interno)         | lbi-        |
| Equilibrador de carga (externo)         | lbe-        |
| Grupo de seguridad de red (NSG)     | nsg-        |
| Grupo de seguridad de aplicaciones (ASG) | asg-        |
| Puerta de enlace de red local            | lgw-        |
| Puerta de enlace de red virtual          | vgw-        |
| Conexión VPN                   | cn-         |
| puerta de enlace de aplicaciones              | agw-        |
| Tabla de rutas                      | route-      |
| Perfil de Traffic Manager          | traf-       |

### <a name="compute-and-web"></a>Procesos y web

| Tipo de recurso                  | Prefijo de nombre |
|-----------------------------|-------------|
| Máquina virtual             | vm          |
| Conjunto de escalado de máquina virtual   | vmss-       |
| Conjunto de disponibilidad            | avail-      |
| Cuenta de almacenamiento de máquina virtual          | stvm        |
| Máquina conectada de Azure Arc | arcm-       |
| Instancia de contenedor          | aci-        |
| Clúster de AKS                 | aks-        |
| Clúster de Service Fabric      | sf-         |
| App Service Environment     | ase-        |
| Plan de App Service            | plan-       |
| Aplicación web                     | app-        |
| Aplicación de función                | func-       |
| servicio en la nube               | cld-        |
| Notification Hubs           | ntf-        |
| Espacio de nombres de Notification Hubs | ntfns-      |

### <a name="databases"></a>Bases de datos

| Tipo de recurso                     | Prefijo de nombre |
|--------------------------------|-------------|
| Servidor de Azure SQL Database      | sql-        |
| Azure SQL Database             | sqldb-      |
| Base de datos de Cosmos DB             | cosmos-     |
| Instancia de Azure Cache for Redis | redis-      |
| Base de datos de MySQL                 | mysql-      |
| Base de datos de PostgreSQL            | psql-       |
| Azure SQL Data Warehouse       | sqldw-      |
| SQL Server Stretch Database    | sqlstrdb-   |

### <a name="storage"></a>Storage

| Tipo de recurso       | Prefijo de nombre |
|------------------|-------------|
| Cuenta de almacenamiento  | st          |
| Azure StorSimple | ssimp       |

### <a name="ai--machine-learning"></a>AI + Aprendizaje automático

| Tipo de recurso                       | Prefijo de nombre |
|----------------------------------|-------------|
| Azure Cognitive Search           | srch-       |
| Azure Cognitive Services         | cog-        |
| Área de trabajo de Azure Machine Learning | mlw-        |

### <a name="analytics-and-iot"></a>Analytics e IoT

| Tipo de recurso                      | Prefijo de nombre |
|---------------------------------|-------------|
| Servidor de Azure Analysis Services  | as-         |
| Área de trabajo de Azure Databricks      | dbw-        |
| Azure Stream Analytics          | asa-        |
| Azure Data Factory              | adf-        |
| Cuenta de Data Lake Store         | dls         |
| Cuenta de Data Lake Analytics     | dla         |
| Centro de eventos                       | evh-        |
| Clúster de HDInsight (Hadoop)      | hadoop-     |
| Clúster de HDInsight (HBase)       | hbase-      |
| Clúster de HDInsight (Kafka)       | kafka-      |
| Clúster de HDInsight (Spark)       | spark-      |
| Clúster de HDInsight (Storm)       | storm-      |
| Clúster de HDInsight (Machine Learning Services) | mls-        |
| centro de IoT                         | iot-        |
| Power BI Embedded               | pbi-        |

### <a name="integration"></a>Integración

| Tipo de recurso        | Prefijo de nombre |
|-------------------|-------------|
| Aplicaciones lógicas        | logic-      |
| Azure Service Bus       | sb-         |
| Cola de Service Bus | sbq-        |
| Tema de Service Bus | sbt-        |

### <a name="management-and-governance"></a>Administración y gobernanza

| Tipo de recurso              | Prefijo de nombre |
|-------------------------|-------------|
| Plano técnico               | bp-         |
| Almacén de claves               | kv-         |
| Área de trabajo de Log Analytics | log-        |
| Application Insights    | appi-       |
| Almacén de Recovery Services | rsv-        |

### <a name="migration"></a>Migración

| Tipo de recurso                          | Prefijo de nombre |
|-------------------------------------|-------------|
| Proyecto de Azure Migrate               | migr-       |
| Instancia de Database Migration Service | dms-        |
| Almacén de Recovery Services             | rsv-        |

<!-- cSpell:enable -->

## <a name="metadata-tags"></a>Etiquetas de metadatos

Al aplicar etiquetas de metadatos a los recursos en la nube, puede incluir información sobre esos recursos que no se pudo incluir en el nombre del recurso. Puede usar esa información para realizar filtrados e informes más elaborados sobre los recursos. Quiere que estas etiquetas incluyan contexto sobre la carga de trabajo o la aplicación asociadas del recurso, los requisitos operativos y la información de propiedad. Esta información la pueden usar los equipos de TI o empresariales para encontrar recursos o generar informes sobre el uso y la facturación de los recursos.

Las etiquetas que se aplican a los recursos y las etiquetas que son necesarias u opcionales varían según la organización. En la lista siguiente se proporcionan ejemplos de etiquetas comunes que capturan contexto e información importantes sobre un recurso. Use esta lista como punto de partida para establecer sus propias convenciones de etiquetado.

| Nombre de etiqueta                  | Descripción                                                                                                                                                                                                          | Clave               | Valor de ejemplo                                              |
|---------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------|------------------------------------------------------------|
| Nombre de la aplicación          | Nombre de la aplicación, servicio o carga de trabajo a la que está asociado el recurso.                                                                                                                                       | _ApplicationName_ | _{app name}_                                               |
| Nombre del aprobador             | Persona responsable de la aprobación de los costos relacionados con este recurso.                                                                                                                                                     | _Approver_        | _{email}_                                                  |
| Presupuesto requerido o aprobado  | Dinero asignado para esta aplicación, servicio o carga de trabajo.                                                                                                                                                          | _BudgetAmount_    | _{\$}_                                                     |
| Unidad de negocio             | División de nivel superior de la empresa que posee la suscripción o la carga de trabajo a la que pertenece el recurso. En organizaciones más pequeñas, esta etiqueta puede representar un solo elemento organizativo de nivel superior corporativo o compartido. | _BusinessUnit_    | _FINANCE_, _MARKETING_, _{Product Name}_ , _CORP_, _SHARED_ |
| Centro de costos               | Centro de costo de contabilidad asociado a este recurso.                                                                                                                                                                | _CostCenter_      | _{number}_                                                 |
| Recuperación ante desastres         | Importancia empresarial de la aplicación, la carga de trabajo o el servicio.                                                                                                                                                       | _DR_              | _Mission-critical_, _Critical_, _Essential_                |
| Fecha de finalización del proyecto   | Fecha en la que la aplicación, la carga de trabajo o el servicio están programados para su retirada.                                                                                                                                         | _EndDate_         | _{date}_                                                   |
| Entorno               | Entorno de implementación de la aplicación, la carga de trabajo o el servicio.                                                                                                                                                     | _Env_             | _Prod_, _Dev_, _QA_, _Stage_, _Test_                       |
| Nombre del propietario                | Propietario de la aplicación, la carga de trabajo o el servicio.                                                                                                                                                                      | _Propietario_           | _{email}_                                                  |
| Nombre del solicitante            | Usuario que solicitó la creación de esta aplicación.                                                                                                                                                                 | _Requestor_       | _{email}_                                                  |
| Clase de servicio             | Nivel de contrato de nivel de servicio de la aplicación, la carga de trabajo o el servicio.                                                                                                                                              | _ServiceClass_    | _Dev_, _Bronze_, _Silver_, _Gold_                          |
| Fecha de inicio del proyecto | Fecha en que se implementó por primera vez la aplicación, la carga de trabajo o el servicio.                                                                                                                                                  | _StartDate_       | _{date}_                                                   |

## <a name="example-names"></a>Nombres de ejemplo

En la siguiente sección se proporcionan algunos ejemplos de nombres para tipos de recursos comunes de Azure en una implementación de nube en la empresa.

<!-- cSpell:disable -->

<!-- markdownlint-disable MD024 MD033 -->

### <a name="example-names-general"></a>Nombres de ejemplo General

| Tipo de recurso                      | Ámbito                              | Formato                                                      | Ejemplos                                                                                                                |
|---------------------------------|------------------------------------|-------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| Subscription                    | Cuenta o <br/>Contrato Enterprise | \<Unidad de negocio\>-\<Tipo de suscripción\>-\<\#\#\#\>          | <ul><li>mktg-prod-001 </li><li>corp-shared-001 </li><li>fin-client-001</li></ul>                                        |
| Resource group                  | Subscription                       | rg-\<nombre de aplicación o servicio\>-\<tipo de suscripción\>-\<\#\#\#\> | <ul><li>rg-mktgsharepoint-prod-001 </li><li>rg-acctlookupsvc-share-001 </li><li>rg-ad-dir-services-shared-001</li></ul> |
| Instancia del servicio API Management | Global                             | apim-\<nombre de aplicación o servicio\>                                | apim-navigator-prod                                                                                                     |

### <a name="example-names-networking"></a>Nombres de ejemplo: Redes

| Tipo de recurso                   | Ámbito           | Formato                                                               | Ejemplos                                                                                                                      |
|------------------------------|-----------------|----------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|
| Virtual network              | Resource group  | vnet-\<tipo de suscripción\>-\<región\>-\<\#\#\#\>                     | <ul><li>vnet-shared-eastus2-001 </li><li>vnet-prod-westus-001 </li><li>vnet-client-eastus2-001</li></ul>                      |
| Subnet                       | Virtual network | snet-\<suscripción\>-\<subregión\>-\<\#\#\#\>                       | <ul><li>snet-shared-eastus2-001 </li><li>snet-prod-westus-001 </li><li>snet-client-eastus2-001</li></ul>                      |
| Tarjeta de interfaz de red (NIC)      | Resource group  | nic-\<\#\#\>-\<nombre de vm\>-\<suscripción\>\<\#\#\#\>                   | <ul><li>nic-01-dc1-shared-001 </li><li>nic-02-vmhadoop1-prod-001 </li><li>nic-02-vmtest1-client-001</li></ul>                 |
| Dirección IP pública            | Resource group  | pip-\<nombre de máquina virtual o nombre de aplicación\>-\<entorno\>-\<subregión\>-\<\#\#\#\> | <ul><li>pip-dc1-shared-eastus2-001 </li><li>pip-hadoop-prod-westus-001</li></ul>                                              |
| Equilibrador de carga                | Resource group  | lb-\<nombre de aplicación o rol\>\<entorno\>\<\#\#\#\>                     | <ul><li>lb-navigator-prod-001 </li><li>lb-sharepoint-dev-001</li></ul>                                                        |
| Grupo de seguridad de red (NSG) | Subred o NIC   | nsg-\<nombre de directiva o nombre de aplicación\>-\<\#\#\#\>                           | <ul><li>nsg-weballow-001 </li><li>nsg-rdpallow-001 </li><li>nsg-sqlallow-001 </li><li>nsg-dnsbloked-001</li></ul>             |
| Puerta de enlace de red local        | Puerta de enlace virtual | lgw-\<tipo de suscripción\>-\<región\>-\<\#\#\#\>                      | <ul><li>lgw-shared-eastus2-001 </li><li>lgw-prod-westus-001 </li><li>lgw-client-eastus2-001</li></ul>                         |
| Puerta de enlace de red virtual      | Virtual network | vgw-\<tipo de suscripción\>-\<región\>-\<\#\#\#\>                      | <ul><li>vgw-shared-eastus2-001 </li><li>vgw-prod-westus-001 </li><li>vgw-client-eastus2-001</li></ul>                         |
| Conexión de sitio a sitio      | Resource group  | cn-\<nombre de puerta de enlace local\>-to-\<nombre de puerta de enlace virtual\>                | <ul><li>cn-lgw-shared-eastus2-001-to-vgw-shared-eastus2-001 </li><li>cn-lgw-shared-eastus2-001-to-shared-westus-001</li></ul> |
| Conexión VPN               | Resource group  | cn-\<suscripción1\>\<región1\>-to-\<subscripción2\>\<región2\>-     | <ul><li>cn-shared-eastus2-to-shared-westus </li><li>cn-prod-eastus2-to-prod-westus</li></ul>                                  |
| Tabla de rutas                  | Resource group  | route-\<nombre de tabla de rutas\>                                           | <ul><li>lb-navigator-prod-001 </li><li>lb-sharepoint-dev-001</li></ul>                                                        |
| Etiqueta DNS                    | Global          | \<un registro de vm\>.[\<región\>.cloudapp.azure.com]                   | <ul><li>dc1.westus.cloudapp.azure.com </li><li>web1.eastus2.cloudapp.azure.com</li></ul>                                      |

### <a name="example-names-compute-and-web"></a>Nombres de ejemplo: Procesos y web

| Tipo de recurso                  | Ámbito          | Formato                                                              | Ejemplos                                                                                                                          |
|-----------------------------|----------------|---------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|
| Máquina virtual             | Resource group | vm\<nombre de directiva o nombre de aplicación\>\<\#\#\#\>                              | <ul><li>vmnavigator001 </li><li>vmsharepoint001 </li><li>vmsqlnode001 </li><li>vmhadoop001</li></ul>                              |
| Cuenta de almacenamiento de máquina virtual          | Global         | stvm\<tipo de rendimiento\>\<nombre de aplicación o nombre de producto\>\<región\>\<\#\#\#\> | <ul><li>stvmstcoreeastus2001 </li><li>stvmpmcoreeastus2001 </li><li>stvmstplmeastus2001 </li><li>stvmsthadoopeastus2001</li></ul> |
| Aplicación web                     | Global         | app-\<nombre de aplicación\>-\<entorno\>-\<\#\#\#\>.[{azurewebsites.net}]   | <ul><li>app-navigator-prod-001.azurewebsites.net </li><li>app-accountlookup-dev-001.azurewebsites.net</li></ul>                   |
| Aplicación de función                | Global         | func-\<nombre de aplicación\>-\<entorno\>-\<\#\#\#\>.[{azurewebsites.net}]  | <ul><li>func-navigator-prod-001.azurewebsites.net </li><li>func-accountlookup-dev-001.azurewebsites.net</li></ul>                 |
| servicio en la nube               | Global         | cld-\<nombre de aplicación\>-\<entorno\>-\<\#\#\#\>.[{cloudapp.net}]        | <ul><li>cld-navigator-prod-001.azurewebsites.net </li><li>cld-accountlookup-dev-001.azurewebsites.net</li></ul>                   |
| Centro de notificaciones            | Resource group | ntf-\<nombre de aplicación\>-\<entorno\>                                    | <ul><li>ntf-navigator-prod </li><li>ntf-emissions-dev</li></ul>                                                                   |
| Espacio de nombres de Notification Hubs | Global         | ntfns-\<nombre de aplicación\>-\<entorno\>                                  | <ul><li>ntfns-navigator-prod </li><li>ntfns-emissions-dev</li></ul>                                                               |

### <a name="example-names-databases"></a>Nombres de ejemplo: Bases de datos

| Tipo de recurso                     | Ámbito              | Formato                                 | Ejemplos                                                                  |
|--------------------------------|--------------------|----------------------------------------|---------------------------------------------------------------------------|
| Servidor de Azure SQL Database      | Global             | sql-\<nombre de aplicación\>-\<entorno\>       | <ul><li>sql-navigator-prod </li><li>sql-emissions-dev</li></ul>           |
| Azure SQL Database             | Azure SQL Database | sqldb-\<nombre de base de datos>-\<entorno\> | <ul><li>sqldb-users-prod </li><li>sqldb-users-dev</li></ul>               |
| Base de datos de Cosmos DB             | Global             | cosmos-\<nombre de aplicación\>-\<entorno\>    | <ul><li>cosmos-navigator-prod </li><li>cosmos-emissions-dev</li></ul>     |
| Instancia de Azure Cache for Redis | Global             | redis-\<nombre de aplicación\>-\<entorno\>     | <ul><li>redis-navigator-prod </li><li>redis-emissions-dev</li></ul>       |
| Base de datos de MySQL                 | Global             | mysql-\<nombre de aplicación\>-\<entorno\>     | <ul><li>mysql-navigator-prod </li><li>mysql-emissions-dev</li></ul>       |
| Base de datos de PostgreSQL            | Global             | sql-\<nombre de aplicación\>-\<entorno\>      | <ul><li>psql-navigator-prod </li><li>psql-emissions-dev</li></ul>         |
| Azure SQL Data Warehouse       | Global             | sqldw-\<nombre de aplicación\>-\<entorno\>     | <ul><li>sqldw-navigator-prod </li><li>sqldw-emissions-dev</li></ul>       |
| SQL Server Stretch Database    | Azure SQL Database | sqlstrdb-\<nombre de aplicación\>-\<entorno\>  | <ul><li>sqlstrdb-navigator-prod </li><li>sqlstrdb-emissions-dev</li></ul> |

### <a name="example-names-storage"></a>Nombres de ejemplo: Storage

| Tipo de recurso                        | Ámbito  | Formato                                                                        | Ejemplos                                                              |
|-----------------------------------|--------|-------------------------------------------------------------------------------|-----------------------------------------------------------------------|
| Cuenta de Storage (uso general)     | Global | st\<nombre de almacenamiento\>\<\#\#\#\>                                                  | <ul><li>stnavigatordata001 </li><li>stemissionsoutput001</li></ul>    |
| Cuenta de Storage (registros de diagnóstico) | Global | stdiag\<primeras dos letras del nombre de la suscripción y el número\>\<región\>\<\#\#\#\> | <ul><li>stdiagsh001eastus2001 </li><li>stdiagsh001westus001</li></ul> |
| Azure StorSimple                  | Global | ssimp\<nombre de aplicación\>\<entorno\>                                              | <ul><li>ssimpnavigatorprod </li><li>ssimpemissionsdev</li></ul>       |

### <a name="example-names-ai--machine-learning"></a>Nombres de ejemplo: AI + Aprendizaje automático

| Tipo de recurso                       | Ámbito          | Formato                            | Ejemplos                                                          |
|----------------------------------|----------------|-----------------------------------|-------------------------------------------------------------------|
| Azure Cognitive Search           | Global         | srch-\<nombre de aplicación\>-\<entorno\> | <ul><li>srch-navigator-prod </li><li>srch-emissions-dev</li></ul> |
| Azure Cognitive Services         | Resource group | cog-\<nombre de aplicación\>-\<entorno\>  | <ul><li>cog-navigator-prod </li><li>cog-emissions-dev</li></ul>   |
| Área de trabajo de Azure Machine Learning | Resource group | mlw-\<nombre de aplicación\>-\<entorno\>  | <ul><li>mlw-navigator-prod </li><li>mlw-emissions-dev</li></ul>   |

### <a name="example-names-analytics-and-iot"></a>Nombres de ejemplo: Analytics e IoT

| Tipo de recurso                  | Ámbito          | Formato                              | Ejemplos                                                              |
|-----------------------------|----------------|-------------------------------------|-----------------------------------------------------------------------|
| Azure Data Factory          | Global         | adf-\<nombre de aplicación\>\<entorno\>     | <ul><li>adf-navigator-prod </li><li>adf-emissions-dev</li></ul>       |
| Azure Stream Analytics      | Resource group | asa-\<nombre de aplicación\>-\<entorno\>    | <ul><li>asa-navigator-prod </li><li>asa-emissions-dev</li></ul>       |
| Cuenta de Data Lake Analytics | Global         | dla\<nombre de aplicación\>\<entorno\>      | <ul><li>dlanavigatorprod </li><li>dlaemissionsdev</li></ul>           |
| Cuenta de Data Lake Storage   | Global         | dls\<nombre de aplicación\>\<entorno\>      | <ul><li>dlsnavigatorprod </li><li>dlsemissionsdev</li></ul>           |
| Centro de eventos                   | Global         | evh-\<nombre de aplicación\>-\<entorno\>    | <ul><li>evh-navigator-prod </li><li>evh-emissions-dev</li></ul>       |
| Clúster de HDInsight (HBase)   | Global         | hbase-\<nombre de aplicación\>-\<entorno\>  | <ul><li>hbase-navigator-prod </li><li>hbase-emissions-dev</li></ul>   |
| Clúster de HDInsight (Hadoop)  | Global         | hadoop-\<nombre de aplicación\>-\<entorno\> | <ul><li>hadoop-navigator-prod </li><li>hadoop-emissions-dev</li></ul> |
| Clúster de HDInsight (Spark)   | Global         | spark-\<nombre de aplicación\>-\<entorno\>  | <ul><li>spark-navigator-prod </li><li>spark-emissions-dev </li></ul>  |
| centro de IoT                     | Global         | iot-\<nombre de aplicación\>-\<entorno\>    | <ul><li>iot-navigator-prod </li><li>iot-emissions-dev</li></ul>       |
| Power BI Embedded           | Global         | pbi-\<nombre de aplicación\>\<entorno\>     | <ul><li>pbi-navigator-prod </li><li>pbi-emissions-dev</li></ul>       |

### <a name="example-names-integration"></a>Nombres de ejemplo: Integración

| Tipo de recurso        | Ámbito       | Formato                                                     | Ejemplos                                                      |
|-------------------|-------------|------------------------------------------------------------|---------------------------------------------------------------|
| Azure Service Bus       | Global      | sb-\<nombre de aplicación\>-\<entorno\>.[{servicebus.windows.net}] | <ul><li>sb-navigator-prod </li><li>sb-emissions-dev</li></ul> |
| Cola de Service Bus | Azure Service Bus | sbq-\<descriptor de consulta\>                                   | <ul><li>sbq-messagequery</li></ul>                            |
| Tema de Service Bus | Azure Service Bus | sbt-\<descriptor de consulta\>                                   | <ul><li>sbt-messagequery</li></ul>                            |
