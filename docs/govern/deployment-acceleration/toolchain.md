---
title: Herramientas de aceleración de la implementación en Azure
description: Compruebe cómo las herramientas nativas de Azure pueden ayudarle a consolidar directivas y procesos que respalden la materia de gobernanza de aceleración de la implementación.
author: BrianBlanchard
ms.author: brblanch
ms.date: 09/17/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: govern
ms.custom: governance
ms.openlocfilehash: ee1c81fe5bada0fa435a598db2f79dc0b23b4392
ms.sourcegitcommit: af45c1c027d7246d1a6e4ec248406fb9a8752fb5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "77709012"
---
# <a name="deployment-acceleration-tools-in-azure"></a>Herramientas de aceleración de la implementación en Azure

[Aceleración de la implementación](./index.md) es una de las [cinco materias de la gobernanza de la nube](../governance-disciplines.md). Esta materia se centra en las distintas maneras de establecer directivas para gobernar la configuración o implementación de recursos. Dentro de las cinco materias de la gobernanza de la nube, la aceleración de la implementación incluye la alineación de la implementación y la configuración. Esto se puede realizar a través de actividades manuales o de actividades de DevOps completamente automatizadas. En cualquier caso, las directivas implicadas seguirían siendo en gran medida las mismas.

Es probable que tanto los guardianes de la nube como los arquitectos de la nube interesados en su gobernanza inviertan mucho tiempo en la materia sobre la aceleración de la implementación, que codifica las directivas y los requisitos en diversos trabajos de adopción de la nube. Las herramientas de esta cadena de herramientas son importantes para el equipo de gobernanza de la nube y deben tener una prioridad alta en la ruta de aprendizaje del equipo.

A continuación, se muestra una lista de las herramientas de Azure que pueden ayudar a desarrollar las directivas y los procesos que admiten esta materia de gobernanza.

|  | [Azure Policy](https://docs.microsoft.com/azure/governance/policy/overview) | [Grupos de administración de Azure](https://docs.microsoft.com/azure/governance/management-groups) | [Azure Resource Manager](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-overview) | [Azure Blueprints](https://docs.microsoft.com/azure/governance/blueprints/overview) | [Azure Resource Graph](https://docs.microsoft.com/azure/governance/resource-graph/overview) | [Azure Cost Management](https://docs.microsoft.com/azure/cost-management) |
|---------|---------|---------|---------|---------|---------|---------|
|Implementación de directivas corporativas     |Sí |Sin  |Sin  |Sin | Sin |Sin |
|Aplicación de directivas a suscripciones     |Obligatorio |Sí  |Sin  |Sin | Sin |Sin |
|Implementación de recursos definidos     |Sin |Sin  |Sí  |Sin | Sin |Sin |
|Creación de entornos totalmente compatibles      |Obligatorio |Obligatorio  |Obligatorio  |Sí | Sin |Sin |
|Auditoría de directivas      |Sí |Sin  |Sin  |Sin | Sin |Sin |
|Consulta de recursos de Azure      |Sin |Sin  |Sin  |Sin |Sí |Sin |
|Informe de costo de recursos      |Sin |Sin  |Sin  |Sin |Sin |Sí |

Las siguientes son herramientas adicionales que pueden ser necesarias para lograr objetivos de aceleración de la implementación concretos. A menudo estas herramientas se usan fuera del equipo de gobernanza, pero se consideran un aspecto de la aceleración de la implementación como materia.

|  | [Azure Portal](https://azure.microsoft.com/features/azure-portal)  | [Azure Resource Manager](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-overview)  | [Azure Policy](https://docs.microsoft.com/azure/governance/policy/overview) | [Azure DevOps](https://docs.microsoft.com/azure/devops/index) | [Azure Backup](https://docs.microsoft.com/azure/backup/backup-introduction-to-azure-backup) | [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview) |
|---------|---------|---------|---------|---------|---------|---------|
|Implementación manual (un solo recurso)     | Sí | Sí  | Sin  | No es eficaz | Sin | Sí |
|Implementación manual (entorno completo)     | No es eficaz | Sí | Sin  | No es eficaz | Sin | Sí |
|Implementación automática (entorno completo)     | Sin  | Sí  | Sin  | Sí  | Sin | Sí |
|Actualización de la configuración de un recurso individual     | Sí | Sí | No es eficaz | No es eficaz | Sin | Si (durante la replicación) |
|Actualización de la configuración de un entorno completo     | No es eficaz | Sí | Sí | Sí  | Sin | Si (durante la replicación) |
|Administración de un desfase de configuración     | No es eficaz | No es eficaz | Sí  | Sí  | Sin | Si (durante la replicación) |
|Creación de una canalización automática para la implementación de código y la configuración de recursos (DevOps)     | Sin | Sin | Sin | Sí | Sin | Sin |

Aparte de las herramientas nativas de Azure que se han mencionado, es habitual que los clientes usen herramientas de terceros para facilitar la aceleración de la implementación y las implementaciones de DevOps.
