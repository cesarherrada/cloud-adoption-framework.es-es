---
title: Herramientas de la coherencia de recursos en Azure
description: Herramientas de la coherencia de recursos en Azure
author: BrianBlanchard
ms.author: brblanch
ms.date: 09/17/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: govern
ms.custom: governance
ms.openlocfilehash: a2f553285f9d44085cc816c2db34f76fcb02235d
ms.sourcegitcommit: 2362fb3154a91aa421224ffdb2cc632d982b129b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76805190"
---
# <a name="resource-consistency-tools-in-azure"></a>Herramientas de la coherencia de recursos en Azure

[Coherencia de recursos](./index.md) es una de las [cinco materias de gobernanza de la nube](../governance-disciplines.md). Esta materia se centra en las distintas formas de establecer directivas relacionadas con la administración operativa de un entorno, una aplicación o una carga de trabajo. En las cinco materias de gobernanza de la nube, la de coherencia de los recursos implica la supervisión del rendimiento de las aplicaciones, las cargas de trabajo y los recursos. También abarca las tareas necesarias para satisfacer las demandas de escala, corregir las infracciones del contrato de nivel de servicio de rendimiento y evitar estas de forma proactiva mediante la corrección automatizada.

A continuación, se muestra una lista de las herramientas de Azure que pueden ayudar a desarrollar las directivas y los procesos que admiten esta materia de gobernanza.

| Herramienta | [Azure Portal](https://azure.microsoft.com/features/azure-portal)  | [Azure Resource Manager](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-overview)  | [Azure Blueprints](https://docs.microsoft.com/azure/governance/blueprints/overview) | [Azure Automation](https://docs.microsoft.com/azure/automation/automation-intro) | [Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) | [Azure Backup](https://docs.microsoft.com/azure/backup/backup-introduction-to-azure-backup) | [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview) |
|---------|---------|---------|---------|---------|---------|---------|---------|
| Implementación de recursos                             | Sí | Sí | Sí | Sí | No  | No | No |
| Administrar recursos                             | Sí | Sí | Sí | Sí | No  | No | No |
| Implementación de recursos mediante plantillas             | No  | Sí | No  | Sí | No  | No | No |
| Implementación de entornos organizada          | No  | No  | Sí | No  | No  | No | No |
| Definición de grupos de recursos                       | Sí | Sí | Sí | No  | No  | No | No |
| Administración de propietarios de cuentas y de cargas de trabajo           | Sí | Sí | Sí | No  | No  | No | No |
| Administración del acceso condicional a los recursos       | Sí | Sí | Sí | No  | No  | No | No |
| Configuración de usuarios de RBAC                         | Sí | No  | No  | No  | Sí | No | No |
| Asignación de roles y permisos a los recursos | Sí | Sí | Sí | No  | Sí | No | No |
| Definición de las dependencias entre recursos        | No  | Sí | Sí | No  | No  | No | No |
| Aplicación del control de acceso                         | Sí | Sí | Sí | No  | Sí | No | No |
| Evaluación de disponibilidad y escalabilidad          | No  | No  | No  | Sí | No  | No | No |
| Aplicación de etiquetas a recursos                      | Sí | Sí | Sí | No  | No  | No | No |
| Asignación de reglas de Azure Policy                    | Sí | Sí | Sí | No  | No  | No | No |
| Aplicación de la corrección automatizada                  | No  | No  | No  | Sí | No  | No | No |
| Administración de facturas                               | Sí | No  | No  | No  | No  | No | No |
| Planeamiento de recursos para la recuperación ante desastres         | Sí | Sí | Sí | No  | No  | Sí | Sí |
|Recuperación de datos durante un corte o una infracción del Acuerdo de Nivel de Servicio     | No | No  | No  | No  | No  | Sí | Sí |
|Recuperación de aplicaciones y datos durante un corte o una infracción del Acuerdo de Nivel de Servicio     | No | No  | No  | No  | No  | Sí | Sí |

Junto con estas características y herramientas de la coherencia de recursos, será preciso que supervise si los recursos implementados tienen problemas de rendimiento y mantenimiento. [Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview) es la solución de supervisión y generación de informes predeterminada de Azure. Azure Monitor proporciona características para supervisar los recursos en la nube. Esta lista muestra qué característica se ocupa de los requisitos de supervisión habituales.

| Herramienta | [Azure Portal](https://azure.microsoft.com/features/azure-portal) | [Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview) | [Log Analytics](https://docs.microsoft.com/azure/azure-monitor/log-query/log-query-overview) | [API Rest de Azure Monitor](https://docs.microsoft.com/rest/api/monitor) |
|----------------------------------------------------|--------------|----------------------|---------------|------------------------|
| Registro de datos de telemetría de máquina virtual                 | No           | No                   | Sí           | No                     |
| Registro de datos de telemetría de redes virtuales              | No           | No                   | Sí           | No                     |
| Registro de datos de telemetría de servicios de PaaS                   | No           | No                   | Sí           | No                     |
| Registro de datos de telemetría de las aplicaciones                     | No           | Sí                  | No            | No                     |
| Configuración de informes y alertas                       | Sí          | No                   | No            | Sí                    |
| Programación de informes periódicos o análisis personalizados        | No           | No                   | No            | No                     |
| Visualización y análisis de datos de rendimiento y registro     | Sí          | No                   | No            | No                     |
| Integración con una solución de supervisión local o de terceros     | No           | No                   | No            | Sí                    |

Al planear la implementación, será preciso que tenga en cuenta dónde se almacenan los datos de registro y cómo se integran los [servicios de supervisión y generación de informes](../../decision-guides/logging-and-reporting/index.md) en la nube con las herramientas y los procesos existentes.

> [!NOTE]
> Las organizaciones también usan herramientas de DevOps de terceros para supervisar las cargas de trabajo y los recursos. Para obtener más información, vea [DevOps Tool Integrations](https://azure.microsoft.com/products/devops-tool-integrations).

## <a name="next-steps"></a>Pasos siguientes

Aprenda a crear, asignar y administrar [definiciones de directivas](https://docs.microsoft.com/azure/governance/policy) en Azure.
