---
title: Implementación de una zona de aterrizaje de migración en Azure
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: Aprenda a implementar una zona de aterrizaje de migración en Azure.
author: BrianBlanchard
ms.author: brblanch
ms.date: 02/25/2020
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: ready
ms.openlocfilehash: 2c9b932bd1a9500b7308fa24be65a12e46221a99
ms.sourcegitcommit: 72a280cd7aebc743a7d3634c051f7ae46e4fc9ae
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2020
ms.locfileid: "78228591"
---
<!-- cSpell:ignore vCPUs jumpbox -->

# <a name="deploy-a-migration-landing-zone"></a>Implementación de una zona de aterrizaje para la migración

La *zona de aterrizaje de migración* es un término que se usa para describir un entorno que se ha aprovisionado y preparado para hospedar las cargas de trabajo que se van a migrar desde un entorno local a Azure.

## <a name="deploy-the-first-landing-zone"></a>Implementación de la primera zona de aterrizaje

Antes de usar el plano técnico de la zona de aterrizaje de migración en Cloud Adoption Framework, revise los siguientes supuestos, decisiones e instrucciones de implementación. Si esta guía se adapta al plan deseado de adopción de la nube, el [ejemplo técnico de la zona de aterrizaje de migración](https://docs.microsoft.com/azure/governance/blueprints/samples/caf-migrate-landing-zone/index) se puede implementar mediante estos [pasos de implementación][deploy-sample].

> [!div class="nextstepaction"]
> [Implementación del ejemplo de plano técnico][deploy-sample]

## <a name="assumptions"></a>Supuestos

Esta zona de aterrizaje inicial incluye las siguientes suposiciones o restricciones. Si estas suposiciones van acordes con las restricciones, puede usar el plano técnico para crear la primera zona de aterrizaje. El plano técnico también se puede ampliar para crear un plano técnico de la zona de aterrizaje que cumpla las restricciones únicas.

- **Límites de suscripción:** no se espera que este esfuerzo de adopción supere los [límites de suscripción](https://docs.microsoft.com/azure/azure-subscription-service-limits). Dos indicadores comunes constituyen un exceso de 25 000 máquinas virtuales o 10 000 vCPU.
- **Cumplimiento:** no se necesita ningún requisito de cumplimiento de terceros en esta zona de aterrizaje.
- **Complejidad de la arquitectura:** la complejidad de la arquitectura no requiere suscripciones de producción adicionales.
- **Servicios compartidos:** no hay servicios compartidos en Azure que requieran que esta suscripción se trate como un radio en una arquitectura en estrella tipo hub-and-spoke.
- **Ámbito de producción limitado:** esta zona de aterrizaje podría hospedar cargas de trabajo de producción. Sin embargo, no constituye un entorno adecuado para los datos confidenciales o las cargas de trabajo críticas.

Si estas suposiciones se adaptan a las necesidades de adopción actuales, este plano técnico podría ser un buen punto de partida para empezar a crear la zona de aterrizaje.

## <a name="decisions"></a>Decisiones

Las siguientes decisiones se representan en el plano técnico de la zona de aterrizaje.

| Componente                    | Decisiones                                                                                         | Enfoques alternativos                                                                                                                                                                                                                                                               |
|------------------------------|---------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Herramientas de migración              | Azure Site Recovery se implementará y se creará un proyecto de Azure Migrate.                | [Guía para la toma de decisiones de las herramientas de migración](../../decision-guides/migrate-decision-guide/index.md)                                                                                                                                                                                              |
| Registro y supervisión       | La cuenta de almacenamiento de diagnóstico y el área de trabajo de Operational Insights se aprovisionarán.                |                                                                                                                                                                                                                                                                                      |
| Red                      | Se creará una red virtual con subredes para la puerta de enlace, el firewall, el jumpbox y la zona de aterrizaje.  | [Decisiones respecto a las redes](../considerations/networking-options.md)                                                                                                                                                                                                                      |
| Identidad                     | Se da por sentado que la suscripción ya está asociada a una instancia de Azure Active Directory. | [Procedimientos recomendados de administración de identidades](https://docs.microsoft.com/azure/security/azure-security-identity-management-best-practices?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/bread/toc.json) |
| Directiva                       | En la actualidad, en este plano técnico se da por hecho que no se aplicará ninguna directiva de Azure.                        |                                                                                                                                                                                                                                                                                      |
| Detalles de la suscripción          | N/A: diseñado para una sola suscripción de producción                                              | [Escalado de suscripciones](../azure-best-practices/scaling-subscriptions.md)                                                                                                                                                                                                            |
| Grupos de administración            | N/A: diseñado para una sola suscripción de producción                                              | [Escalado de suscripciones](../azure-best-practices/scaling-subscriptions.md)                                                                                                                                                                                                            |
| Grupos de recursos              | N/A: diseñado para una sola suscripción de producción                                              | [Escalado de suscripciones](../azure-best-practices/scaling-subscriptions.md)                                                                                                                                                                                                            |
| data                         | N/D                                                                                               | [Elección de la opción correcta de SQL Server en Azure](https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas) y [Guía sobre Azure Data Lake Store](https://docs.microsoft.com/azure/architecture/guide/technology-choices/data-store-overview)                      |
| Storage                      | N/D                                                                                               | [Guía de Azure Storage](../considerations/storage-options.md)                                                                                                                                                                                                                       |
| Estándares de nomenclatura y etiquetado | N/D                                                                                               | [Procedimientos recomendados de nomenclatura y etiquetado](../azure-best-practices/naming-and-tagging.md)                                                                                                                                                                                                   |
| Administración de costos              | N/D                                                                                               | [Seguimiento de costos](../azure-best-practices/track-costs.md)                                                                                                                                                                                                                             |
| Proceso                      | N/D                                                                                               | [Opciones de proceso](../considerations/compute-options.md)                                                                                                                                                                                                                              |

## <a name="customize-or-deploy-a-landing-zone"></a>Personalización o implementación de una zona de aterrizaje

Obtenga más información y descargue un ejemplo de referencia del plano técnico de la zona de aterrizaje de migración para la implementación o personalización a partir de [ejemplos de Azure Blueprints][deploy-sample].

> [!div class="nextstepaction"]
> [Implementación del ejemplo de plano técnico][deploy-sample]

Para obtener instrucciones sobre la personalización que se debe realizar en este plano técnico o la zona de aterrizaje resultante, consulte las [consideraciones de zona de aterrizaje](../considerations/index.md).

## <a name="next-steps"></a>Pasos siguientes

Después de implementar la primera zona de aterrizaje, ya está listo para [expandirla](../considerations/index.md)

> [!div class="nextstepaction"]
> [Expansión de la zona de aterrizaje](../considerations/index.md)

<!-- links -->

[deploy-sample]: https://docs.microsoft.com/azure/governance/blueprints/samples/caf-migrate-landing-zone/deploy