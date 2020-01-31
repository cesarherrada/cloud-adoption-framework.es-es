---
title: Herramientas de aceleración de la implementación en Azure
description: Herramientas de aceleración de la implementación en Azure
author: BrianBlanchard
ms.author: brblanch
ms.date: 09/17/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: govern
ms.custom: governance
ms.openlocfilehash: 6617fe95f885836241e4b0f16bc17652f36c5a7d
ms.sourcegitcommit: 2362fb3154a91aa421224ffdb2cc632d982b129b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76806329"
---
# <a name="deployment-acceleration-tools-in-azure"></a>Herramientas de aceleración de la implementación en Azure

[Aceleración de la implementación](./index.md) es una de las [cinco materias de la gobernanza de la nube](../governance-disciplines.md). Esta materia se centra en las distintas maneras de establecer directivas para gobernar la configuración o implementación de recursos. Dentro de las cinco materias de la gobernanza de la nube, la aceleración de la implementación incluye la alineación de la implementación y la configuración. Esto se puede realizar a través de actividades manuales o de actividades de DevOps completamente automatizadas. En cualquier caso, las directivas implicadas seguirían siendo en gran medida las mismas.

Es probable que tanto los guardianes de la nube como los arquitectos de la nube interesados en su gobernanza inviertan mucho tiempo en la materia sobre la aceleración de la implementación, que codifica las directivas y los requisitos en diversos trabajos de adopción de la nube. Las herramientas de esta cadena de herramientas son importantes para el equipo de gobernanza de la nube y deben tener una prioridad alta en la ruta de aprendizaje del equipo.

A continuación, se muestra una lista de las herramientas de Azure que pueden ayudar a desarrollar las directivas y los procesos que admiten esta materia de gobernanza.

|  | [Azure Policy](https://docs.microsoft.com/azure/governance/policy/overview) | [Grupos de administración de Azure](https://docs.microsoft.com/azure/governance/management-groups) | [Azure Resource Manager](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-overview) | [Azure Blueprints](https://docs.microsoft.com/azure/governance/blueprints/overview) | [Azure Resource Graph](https://docs.microsoft.com/azure/governance/resource-graph/overview) | [Azure Cost Management](https://docs.microsoft.com/azure/cost-management) |
|---------|---------|---------|---------|---------|---------|---------|
|Implementación de directivas corporativas     |Sí |No  |No  |No | No |No |
|Aplicación de directivas a suscripciones     |Obligatorio |Sí  |No  |No | No |No |
|Implementación de recursos definidos     |No |No  |Sí  |No | No |No |
|Creación de entornos totalmente compatibles      |Obligatorio |Obligatorio  |Obligatorio  |Sí | No |No |
|Auditoría de directivas      |Sí |No  |No  |No | No |No |
|Consulta de recursos de Azure      |No |No  |No  |No |Sí |No |
|Informe de costo de recursos      |No |No  |No  |No |No |Sí |

Las siguientes son herramientas adicionales que pueden ser necesarias para lograr objetivos de aceleración de la implementación concretos. A menudo estas herramientas se usan fuera del equipo de gobernanza, pero se consideran un aspecto de la aceleración de la implementación como materia.

|  | [Azure Portal](https://azure.microsoft.com/features/azure-portal)  | [Azure Resource Manager](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-overview)  | [Azure Policy](https://docs.microsoft.com/azure/governance/policy/overview) | [Azure DevOps](https://docs.microsoft.com/azure/devops/index) | [Azure Backup](https://docs.microsoft.com/azure/backup/backup-introduction-to-azure-backup) | [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview) |
|---------|---------|---------|---------|---------|---------|---------|
|Implementación manual (un solo recurso)     | Sí | Sí  | No  | No es eficaz | No | Sí |
|Implementación manual (entorno completo)     | No es eficaz | Sí | No  | No es eficaz | No | Sí |
|Implementación automática (entorno completo)     | No  | Sí  | No  | Sí  | No | Sí |
|Actualización de la configuración de un recurso individual     | Sí | Sí | No es eficaz | No es eficaz | No | Si (durante la replicación) |
|Actualización de la configuración de un entorno completo     | No es eficaz | Sí | Sí | Sí  | No | Si (durante la replicación) |
|Administración de un desfase de configuración     | No es eficaz | No es eficaz | Sí  | Sí  | No | Si (durante la replicación) |
|Creación de una canalización automática para la implementación de código y la configuración de recursos (DevOps)     | No | No | No | Sí | No | No |

Aparte de las herramientas nativas de Azure que se han mencionado, es habitual que los clientes usen herramientas de terceros para facilitar la aceleración de la implementación y las implementaciones de DevOps.
