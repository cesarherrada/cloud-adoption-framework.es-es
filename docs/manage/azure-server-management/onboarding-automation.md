---
title: Automatizar la incorporación
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: Automatizar la incorporación
author: BrianBlanchard
ms.author: brblanch
ms.date: 05/10/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.openlocfilehash: f5dd418a03dd35ebced1a9c73eb8fe6567339859
ms.sourcegitcommit: bf9be7f2fe4851d83cdf3e083c7c25bd7e144c20
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73565406"
---
# <a name="automate-onboarding"></a>Automatizar la incorporación

Para mejorar la eficacia de la implementación de los servicios de administración de servidores de Azure, considere la posibilidad de automatizar la implementación como se describe en las secciones anteriores de esta guía. El script y las plantillas de ejemplo que se proporcionan en las siguientes secciones son puntos de partida para desarrollar su propia automatización de procesos de incorporación.

Esta guía tiene un repositorio de código de ejemplo de GitHub complementario, [CloudAdoptionFramework](https://aka.ms/caf/manage/automation-samples). El repositorio proporciona scripts y plantillas de Azure Resource Manager de ejemplo que le ayudarán a automatizar la implementación de los servicios de administración de servidores de Azure.

En estos archivos de ejemplo se muestra cómo usar los cmdlets de Azure PowerShell para automatizar estas tareas:

- Crear un [área de trabajo de Log Analytics](https://docs.microsoft.com/azure/azure-monitor/platform/manage-access). (O bien, use un área de trabajo existente si cumple los requisitos. Para obtener más información, consulte el tema sobre el [planeamiento del área de trabajo](./prerequisites.md#log-analytics-workspace-and-automation-account-planning)).

- Crear una cuenta de Automation. (O bien, use una cuenta existente si cumple los requisitos. Para obtener más información, consulte el tema sobre el [planeamiento del área de trabajo](./prerequisites.md#log-analytics-workspace-and-automation-account-planning)).

- Vincular cuenta de Automation y el área de trabajo de Log Analytics. Este paso no es necesario si realiza la incorporación mediante Azure Portal.

- Habilitar Update Management y Change Tracking e Inventario para el área de trabajo.

- Incorporar VM de Azure mediante Azure Policy. Una directiva instala el agente de Log Analytics y Microsoft Dependency Agent en las VM de Azure.

- Incorporar los servidores locales mediante la instalación del agente de Log Analytics en ellos.

Los archivos que se describen en la tabla siguiente se usan en este ejemplo. Puede personalizarlos para que admitan sus propios escenarios de implementación.

| Nombre de archivo | DESCRIPCIÓN |
|-----------|-------------|
| New-AMSDeployment.ps1 | Script de orquestación principal que automatiza la incorporación. Crea grupos de recursos, la ubicación, el área de trabajo y las cuentas de Automation, si aún no existen. Este script de PowerShell requiere una suscripción existente. |
| Workspace-AutomationAccount.json | Plantilla de Resource Manager que implementa el área de trabajo y los recursos de la cuenta de Automation. |
| WorkspaceSolutions.json | Plantilla de Resource Manager que habilita las soluciones que quiere en el área de trabajo de Log Analytics. |
| ScopeConfig.json | Plantilla de Resource Manager que usa el modelo de participación para servidores locales con la solución Change Tracking. El uso del modelo de participación es opcional. |
| Enable-VMInsightsPerfCounters.ps1 | Script de PowerShell que habilita VM Insights para los servidores y configura los contadores de rendimiento. |
| ChangeTracking-Filelist.json | Plantilla de Resource Manager que define la lista de archivos que se supervisarán mediante Change Tracking. |

Utilice el comando siguiente para ejecutar New-AMSDeployment.ps1:

```powershell
.\New-AMSDeployment.ps1 -SubscriptionName '{Subscription Name}' -WorkspaceName '{Workspace Name}' -WorkspaceLocation '{Azure Location}' -AutomationAccountName {Account Name} -AutomationAccountLocation {Account Location}
```

## <a name="next-steps"></a>Pasos siguientes

Aprenda a configurar alertas básicas para informar al equipo de problemas y eventos de administración esenciales.

> [!div class="nextstepaction"]
> [Configuración de alertas básicas](./setup-alerts.md)
