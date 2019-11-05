---
title: Uso de Terraform para crear zonas de aterrizaje
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: Obtenga información sobre le uso de Terraform para crear zonas de aterrizaje.
author: arnaudlh
ms.author: arnaul
ms.date: 10/16/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: ready
ms.openlocfilehash: 51751ab0033505e34c02c17db363bc985b83e44d
ms.sourcegitcommit: e0a783dac15bc4c41a2f4ae48e1e89bc2dc272b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73058153"
---
# <a name="use-terraform-to-build-your-landing-zones"></a>Uso de Terraform para crear zonas de aterrizaje

Azure proporciona servicios nativos para implementar las zonas de aterrizaje. Otras herramientas de terceros también pueden ayudarle con este trabajo. Una herramienta de este tipo que los clientes y asociados suelen usar para implementar zonas de aterrizaje es Terraform de HashiCorp. En esta sección se muestra cómo usar un prototipo de zona de aterrizaje para implementar funcionalidades de registro, contabilidad y seguridad fundamentales para una suscripción de Azure.

## <a name="purpose-of-the-landing-zone"></a>Propósito de la zona de aterrizaje

La zona de aterrizaje básica de Cloud Adoption Framework para Terraform tiene un conjunto limitado de responsabilidades y características para aplicar las funcionalidades de registro, contabilidad y seguridad. Esta zona de aterrizaje se diseñó para usar componentes estándar conocidos como módulos de Terraform para aplicar la coherencia entre los recursos implementados en el entorno.

## <a name="using-standard-modules"></a>Uso de módulos estándar

La reutilización de componentes es un principio fundamental de la infraestructura como código. Los módulos son fundamentales para definir los estándares y la coherencia a través de la implementación de recursos dentro y entre entornos. El conjunto de módulos usados para implementar esta primera zona de aterrizaje está disponible en el [registro de Terraform](https://registry.terraform.io/search?q=aztfmod) oficial.

## <a name="architecture-diagram"></a>Diagrama de la arquitectura

La primera zona de aterrizaje implementa los siguientes componentes en su suscripción:

![Zona de aterrizaje básica con Terraform](../../_images/ready/foundations-terraform-landingzone.png)

## <a name="capabilities"></a>Capacidades

Los componentes implementados y su finalidad incluyen lo siguiente:

| Componente | Responsabilidad |
|---------|---------|
| Grupos de recursos | Grupos de recursos principales necesarios para la base |
| Registro de actividad | Realizar la auditoría de todas las actividades de suscripción y el archivado: </br> - Cuenta de almacenamiento </br> - Event Hubs |  
| Registro de diagnóstico | Registro de todas las operaciones que se mantiene durante un número específico de días: </br> - Cuenta de almacenamiento </br> - Event Hubs |
| Log Analytics | Almacena todos los registros de operaciones </br> Implementar soluciones comunes para la revisión profunda de los procedimientos recomendados de aplicaciones: </br> - NetworkMonitoring </br> - ADAssessment </br> - ADReplication </br> - AgentHealthAssessment </br> - DnsAnalytics </br> - KeyVaultAnalytics
| Security Center | Métricas de higiene de seguridad y alertas enviadas al correo electrónico y al número de teléfono |

## <a name="use-this-blueprint"></a>Uso de este plano técnico

Antes de usar la zona de aterrizaje básica de Cloud Adoption Framework, revise los supuestos, las decisiones y las instrucciones de implementación siguientes.

## <a name="assumptions"></a>Supuestos

Las siguientes suposiciones o restricciones se tuvieron en cuenta cuando se definió esta zona de aterrizaje inicial. Si estas suposiciones van acordes con las restricciones, puede usar el plano técnico para crear la primera zona de aterrizaje. El plano técnico también se puede ampliar para crear un plano técnico de la zona de aterrizaje que cumpla las restricciones únicas.

- **Límites de suscripción:** no es probable que este trabajo de adopción supere los [límites de suscripción](https://docs.microsoft.com/azure/azure-subscription-service-limits). Dos indicadores comunes constituyen un exceso de 25 000 máquinas virtuales o 10 000 vCPU.
- **Cumplimiento:** no se necesita ningún requisito de cumplimiento de terceros para esta zona de aterrizaje.
- **Complejidad de la arquitectura:** la complejidad de la arquitectura no requiere suscripciones de producción adicionales.
- **Servicios compartidos:** no hay servicios compartidos en Azure que requieran que esta suscripción se trate como un radio en una arquitectura de concentrador y radio.

Si estas suposiciones coinciden con su entorno actual, este plano técnico podría ser un buen punto de partida para empezar a crear la zona de aterrizaje.

## <a name="design-decisions"></a>Decisiones de diseño

Las siguientes decisiones se representan en la zona de aterrizaje de Terraform:

| Componente | Decisiones | Enfoques alternativos |
| --- | --- | --- |
|Registro y supervisión | Se usará el área de trabajo de Log Analytics de Azure Monitor. Se aprovisionarán una cuenta de almacenamiento de diagnósticos y un centro de eventos. |         |
|Red | N/A: la red se implementará en otra zona de aterrizaje. |[Decisiones respecto a las redes](../considerations/network-decisions.md) |
|Identidad | Se da por sentado que la suscripción ya está asociada a una instancia de Azure Active Directory. | [Procedimientos recomendados de administración de identidades](https://docs.microsoft.com/azure/security/azure-security-identity-management-best-practices) |
| Directiva | En la actualidad, en esta zona de aterrizaje se da por hecho que no se aplicará ninguna directiva de Azure. | |
|Detalles de la suscripción | N/A: diseñado para una sola suscripción de producción | [Escalado de suscripciones](../considerations/scaling-subscriptions.md) |
| Grupos de administración | N/A: diseñado para una sola suscripción de producción |[Escalado de suscripciones](../considerations/scaling-subscriptions.md) |
| Grupos de recursos | N/A: diseñado para una sola suscripción de producción | [Escalado de suscripciones](../considerations/scaling-subscriptions.md) |
| Datos | N/D | [Elección de la opción correcta de SQL Server en Azure](https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas) y [Guía sobre Azure Data Lake Store](https://docs.microsoft.com/azure/architecture/guide/technology-choices/data-store-overview) |
|Storage|N/D|[Guía de Azure Storage](../considerations/storage-guidance.md) |
| Estándares de nomenclatura | Cuando se cree el entorno, también se creará un prefijo único. Los recursos que requieren un nombre único global (como las cuentas de almacenamiento) utilizan este prefijo. El nombre personalizado se anexará con un sufijo aleatorio. El uso de etiquetas se ordena como se describe en la tabla siguiente. | [Procedimientos recomendados de nomenclatura y etiquetado](../considerations/naming-and-tagging.md) |
| Administración de costos | N/D | [Seguimiento de costos](../azure-best-practices/track-costs.md) |
| Proceso | N/D | [Opciones de proceso](../considerations/compute-decisions.md) |

### <a name="tagging-standards"></a>Estándares de etiquetado

El conjunto de etiquetas mínimas siguiente debe estar presente en todos los recursos y grupos de recursos:

| Nombre de etiqueta | DESCRIPCIÓN | Clave | Valor de ejemplo |
|--|--|--|--|
| Unidad de negocio | División de nivel superior de la empresa que posee la suscripción o la carga de trabajo a la que pertenece el recurso. | BusinessUnit | FINANCE, MARKETING, {Product Name}, CORP, SHARED |
| Centro de costo | Centro de costo de contabilidad asociado a este recurso.| CostCenter | Number |
| Recuperación ante desastres | Importancia empresarial de la aplicación, la carga de trabajo o el servicio. | DR | DR-ENABLED, NON-DR-ENABLED |
| Entorno | Entorno de implementación de la aplicación, la carga de trabajo o el servicio. |  Env | Prod, Dev, QA, Stage, Test, Training |
| Nombre del propietario | Propietario de la aplicación, la carga de trabajo o el servicio.| Propietario | email |
| DeploymentType | Define cómo se mantienen los recursos. | deploymentType | Manual, Terraform |
| Versión | Versión del plano técnico implementado | version | v0.1 |
| Nombre de la aplicación | Nombre de la aplicación, el servicio o la carga de trabajo que se ha asociado al recurso. | ApplicationName | "app name" |

## <a name="customize-and-deploy-your-first-landing-zone"></a>Personalizar e implementar la primera zona de aterrizaje

Puede [clonar la zona de aterrizaje básica de Terraform](https://github.com/microsoft/CloudAdoptionFramework/tree/master/ready). Es fácil empezar a trabajar con la zona de aterrizaje con la modificación de las variables de Terraform. En nuestro ejemplo, usamos **blueprint_foundations.sandbox.auto.tfvars**, de modo que Terraform establecerá automáticamente los valores de este archivo.

Echemos un vistazo a las diferentes secciones de variables.

En este primer objeto, se crean dos grupos de recursos en la región `southeastasia`, denominada "-hub-core-sec" y "-hub-core-sec" junto con un prefijo agregado en tiempo de ejecución.

```hcl
resource_groups_hub = {
    HUB-CORE-SEC    = {
        name = "-hub-core-sec"
        location = "southeastasia"
    }
    HUB-OPERATIONS  = {
        name = "-hub-operations"
        location = "southeastasia"
    }
}
```

A continuación, se especifican las regiones en las que se pueden establecer las bases. En este caso, se utilizará `southeastasia` para implementar todos los recursos.

```hcl
location_map = {
    region1   = "southeastasia"
    region2   = "eastasia"
}
```

A continuación, se especifica el período de retención para los registros de operaciones y los registros de suscripción de Azure. Estos datos se almacenarán en cuentas de almacenamiento independientes y en un centro de eventos, cuyos nombres se generan de forma aleatoria, ya que deben ser únicos.

```hcl
azure_activity_logs_retention = 365
azure_diagnostics_logs_retention = 60
```

En tags_hub, se especifica el conjunto mínimo de etiquetas que se aplicarán a todos los recursos creados.

```hcl
tags_hub = {
    environment     = "DEV"
    owner           = "Arnaud"
    deploymentType  = "Terraform"
    costCenter      = "65182"
    BusinessUnit    = "SHARED"
    DR              = "NON-DR-ENABLED"
}
```

A continuación, se especifica el nombre del análisis de registros y un conjunto de soluciones que analizarán la implementación. Aquí se conservan las características de supervisión de red, AD Assessment, replicación de AD, DNS Analytics y Key Vault Analytics.

```hcl

analytics_workspace_name = "lalogs"

solution_plan_map = {
    NetworkMonitoring = {
        "publisher" = "Microsoft"
        "product"   = "OMSGallery/NetworkMonitoring"
    },
    ADAssessment = {
        "publisher" = "Microsoft"
        "product"   = "OMSGallery/ADAssessment"
    },
    ADReplication = {
        "publisher" = "Microsoft"
        "product"   = "OMSGallery/ADReplication"
    },
    AgentHealthAssessment = {
        "publisher" = "Microsoft"
        "product"   = "OMSGallery/AgentHealthAssessment"
    },
    DnsAnalytics = {
        "publisher" = "Microsoft"
        "product"   = "OMSGallery/DnsAnalytics"
    },
    KeyVaultAnalytics = {
        "publisher" = "Microsoft"
        "product"   = "OMSGallery/KeyVaultAnalytics"
    }
}

```

A continuación, se configuran los parámetros de alerta de Azure Security Center.

```hcl
# Azure Security Center Configuration
security_center = {
    contact_email   = "joe@contoso.com"
    contact_phone   = "+6500000000"
}
```

## <a name="getting-started"></a>Introducción

Una vez que haya revisado la configuración, podrá implementar la configuración como implementaría un entorno de Terraform. Sin embargo, se recomienda usar el róver, que es un contenedor de Docker que permite la implementación desde Windows, Linux o MacOS. Puede empezar a usar el [repositorio de GitHub del róver](https://github.com/aztfmod/rover).

## <a name="next-steps"></a>Pasos siguientes

La zona de aterrizaje básica establece la base para un entorno complejo de forma descompuesta. Esta edición proporciona un conjunto de funcionalidades muy simples que se puede ampliar de la siguiente manera:

- Agregando otros módulos al plano técnico.
- Distribuyendo capas de zonas de aterrizaje adicionales encima suyo.

La distribución en capas de las zonas de aterrizaje es una buena práctica para desacoplar sistemas, realizar el control de versiones de cada componente que utiliza, y permitir la innovación y la estabilidad rápidas para su implementación de infraestructura como código.

Las arquitecturas de referencia futuras mostrarán este concepto para una topología de concentrador y radio.

> [!div class="nextstepaction"]
> [Revisar la zona de aterrizaje básica con Terraform](https://github.com/microsoft/CloudAdoptionFramework/tree/master/ready)
