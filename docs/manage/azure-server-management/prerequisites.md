---
title: Planeamiento de los requisitos previos de los servicios de administración de servidores de Azure
description: Herramientas y planeamiento de los requisitos previos de los servicios de administración de servidores de Azure
author: BrianBlanchard
ms.author: brblanch
ms.date: 05/10/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.openlocfilehash: 934263f5c143d021ce97125f025f96d8ae6f338f
ms.sourcegitcommit: 2362fb3154a91aa421224ffdb2cc632d982b129b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76807978"
---
# <a name="phase-1-prerequisite-planning-for-azure-server-management-services"></a>Fase 1: Planeamiento de los requisitos previos de los servicios de administración de servidores de Azure

En esta fase, se familiarizará con el conjunto de servicios de administración de servidores de Azure y planeará la implementación de los recursos necesarios para implementar estas soluciones de administración.

## <a name="understand-the-tools-and-services"></a>Descripción de las herramientas y los servicios

Consulte [Servicios y herramientas de administración de servidores de Azure](./tools-services.md) para obtener información general detallada sobre:

- Las áreas de administración que intervienen en las operaciones de Azure en curso.
- Los servicios y las herramientas de Azure que le ayudan en estas áreas.

Para cumplir los requisitos de administración, deberá usar varios de estos servicios. Nos referiremos a estas herramientas con frecuencia a lo largo de esta guía.

En las secciones siguientes se describen el planeamiento y la preparación necesarios para utilizar estas herramientas y los servicios.

## <a name="log-analytics-workspace-and-automation-account-planning"></a>Planeamiento del área de trabajo de Log Analytics y cuenta de Azure Automation

Muchos de los servicios que usará para incorporar los servicios de administración de Azure requieren un área de trabajo de Log Analytics y una cuenta de Azure Automation vinculada.

Un [área de trabajo de Log Analytics](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) es un entorno único para almacenar los datos de registro de Azure Monitor. Cada área de trabajo tiene su propio repositorio y configuración de datos. Los orígenes de datos y las soluciones se configuran para almacenar sus datos en áreas de trabajo determinadas. Las soluciones de supervisión de Azure requieren que todos los servidores se conecten a un área de trabajo, para poder almacenar los datos de registro y obtener acceso a ellos.

Algunos de los servicios de administración requieren una cuenta de [Azure Automation](https://docs.microsoft.com/azure/automation/automation-intro). Esta cuenta y las funcionalidades de Azure Automation se usan para integrar los servicios de Azure y otros sistemas públicos para implementar, configurar y administrar los procesos de administración de servidores.

Los siguientes servicios de administración de servidores de Azure requieren un área de trabajo de Log Analytics vinculada y una cuenta de Automation:

- [Azure Update Management](https://docs.microsoft.com/azure/automation/automation-update-management)
- [Change Tracking e Inventario](https://docs.microsoft.com/azure/automation/change-tracking)
- [Trabajo híbrido de runbook](https://docs.microsoft.com/azure/automation/automation-hybrid-runbook-worker)
- [Desired State Configuration](https://docs.microsoft.com/azure/virtual-machines/extensions/dsc-overview)

La segunda fase de esta guía se centra en la implementación de los servicios y los scripts de automatización. Muestra cómo crear un área de trabajo de Log Analytics y una cuenta de Azure Automation. En esta guía también se muestra cómo usar Azure Policy para asegurarse de que las nuevas máquinas virtuales estén conectadas al área de trabajo correcta.

En los ejemplos de esta guía se da por hecho que hay una implementación que aún no tiene servidores implementados en la nube. Para más información sobre los principios y las consideraciones que conlleva el planeamiento de las áreas de trabajo, consulte [Administración de los datos de registro y las áreas de trabajo en Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/platform/manage-access).

## <a name="planning-considerations"></a>Consideraciones de planeación

Al preparar las áreas de trabajo y las cuentas que necesita para incorporar los servicios de administración, tenga en cuenta los siguientes problemas:

- **Zonas geográficas de Azure y cumplimiento normativo:** Las regiones de Azure se organizan por *zonas geográficas*. Una [zona geográfica de Azure](https://azure.microsoft.com/global-infrastructure/geographies) garantiza que se cumplan los requisitos de residencia, soberanía, cumplimiento normativo y resistencia de los datos dentro de las fronteras geográficas. Si las cargas de trabajo están sujetas a la soberanía de datos u otros requisitos de cumplimiento, las cuentas de Azure Automation y el área de trabajo deben implementarse en regiones dentro de la misma ubicación geográfica de Azure que los recursos de la carga de trabajo a los que corresponden.
- **Número de áreas de trabajo:** Como regla general, cree el número mínimo de áreas de trabajo necesarias por ubicación geográfica de Azure. Se recomienda al menos un área de trabajo para cada zona geográfica de Azure donde se encuentren los recursos de proceso o almacenamiento. Esta alineación inicial ayuda a evitar problemas normativos futuros al migrar datos a zonas geográficas diferentes.
- **Límite y retención de los datos:** También es posible que deba tener en cuenta las directivas de retención de datos o los requisitos de límite de datos al crear áreas de trabajo o cuentas de Azure Automation. Para más información sobre los estos principios y las consideraciones adicionales que conlleva el planeamiento de las áreas de trabajo, consulte [Administración de los datos de registro y las áreas de trabajo en Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/platform/manage-access).
- **Asignación de región:** solo se pueden vincular un área de trabajo de Log Analytics y una cuenta de Azure Automation entre determinadas regiones de Azure. Por ejemplo, si el área de trabajo de Log Analytics se hospeda en la región *EastUS*, la cuenta de Azure Automation vinculada se debe crear en la región *EastUS2* para poder usarse con los servicios de administración. Si tiene una cuenta de Automation creada en otra región, no podrá vincularla a un área de trabajo en *EastUS*. La elección de la región de implementación puede afectar significativamente a los requisitos de zona geográfica de Azure. Consulte la [tabla de asignación de regiones](https://docs.microsoft.com/azure/automation/how-to/region-mappings) para decidir qué región debe hospedar las áreas de trabajo y las cuentas de Automation.
- **Hospedaje múltiple de áreas de trabajo:** el agente de Azure Log Analytics admite el hospedaje múltiple en algunos escenarios, pero se esta configuración presenta varias limitaciones y retos. A menos que Microsoft lo recomiende para su escenario, no se recomienda configurar el host múltiple en el agente de Log Analytics.

## <a name="resource-placement-examples"></a>Ejemplos de ubicación de recursos

Hay varios modelos diferentes para elegir la suscripción en la que se colocan el área de trabajo de Log Analytics y la cuenta de Automation. En resumen, coloque el área de trabajo y las cuentas de Automation en una suscripción que sea propiedad del equipo responsable de la implementación de los servicios Update Management y Change Tracking e Inventario.

A continuación se muestran ejemplos de algunas formas de implementar áreas de trabajo y cuentas de Automation.

### <a name="placement-by-geography"></a>Ubicación por zona geográfica

Los entornos pequeños y medianos tienen una sola suscripción y varios cientos de recursos que abarcan varias zonas geográficas de Azure. Para estos entornos, cree un área de trabajo Log Analytics y una cuenta de Azure Automation en cada zona geográfica.

Puede crear un área de trabajo y una cuenta de Azure Automation como un par en cada grupo de recursos. A continuación, implemente el par de la zona geográfica correspondiente en las máquinas virtuales.

Como alternativa, si las directivas de cumplimiento de datos no dictan que los recursos residan en regiones específicas, puede crear un par para administrar todas las máquinas virtuales. También se recomienda colocar los pares de área de trabajo y cuenta de Automation en grupos de recursos independientes para proporcionar un control de acceso basado en rol (RBAC) más detallado.

El ejemplo del diagrama siguiente tiene una suscripción con dos grupos de recursos, cada uno de los cuales se encuentra en una zona geográfica diferente:

![Modelo de área de trabajo para entornos pequeños a medianos](./media/workspace-model-small.png)

### <a name="placement-in-a-management-subscription"></a>Ubicación en una suscripción de administración

Los entornos más grandes abarcan varias suscripciones y tienen un departamento de TI central propietario de la supervisión y el cumplimiento. Para estos entornos, cree pares de áreas de trabajo y cuentas de Automation en una suscripción de administración de TI. En este modelo, los recursos de máquina virtual situados en una zona geográfica almacenan sus datos en el área de trabajo de la zona geográfica correspondiente, en la suscripción de administración de TI. Si los equipos de aplicaciones necesitan ejecutar tareas de automatización, pero no requieren un área de trabajo vinculada ni cuentas de Automation, pueden crear cuentas de Automation independientes en sus propias suscripciones de aplicación.

![Modelo de área de trabajo para entornos de gran tamaño](./media/workspace-model-large.png)

### <a name="decentralized-placement"></a>Ubicación descentralizada

En un modelo alternativo para entornos de gran tamaño, el equipo de desarrollo de aplicaciones puede tener la responsabilidad de la administración y aplicación de revisiones. En este caso, coloque los pares de área de trabajo y cuenta de Automation en las suscripciones del equipo de aplicaciones, junto con los demás recursos.

  ![Modelo de cuenta de área de trabajo para entornos descentralizados](./media/workspace-model-decentralized.png)

## <a name="create-a-workspace-and-automation-account"></a>Creación de un área de trabajo y una cuenta de Automation

Después de elegir la mejor manera de colocar y organizar los pares de área de trabajo y cuenta, asegúrese de crear estos recursos antes de iniciar el proceso de incorporación. En los ejemplos de automatización que se incluyen más adelante en esta guía, se crea automáticamente un par de área de trabajo y cuenta de Automation. Sin embargo, si quiere realizar la incorporación mediante Azure Portal y no tiene ningún par de área de trabajo y cuenta de Automation, tendrá que crear uno.

Para crear un área de trabajo de Log Analytics mediante Azure Portal, consulte [Creación de un área de trabajo](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace#create-a-workspace). A continuación, cree la cuenta de Automation correspondiente a cada área de trabajo siguiendo los pasos descritos en [Creación de una cuenta de Azure Automation](https://docs.microsoft.com/azure/automation/automation-quickstart-create-account).

> [!NOTE]
> Al crear una cuenta de Automation mediante Azure Portal, el portal intenta de forma predeterminada crear cuentas de ejecución para los recursos de Azure Resource Manager y del modelo de implementación clásica. Si no tiene máquinas virtuales clásicas en su entorno y no es coadministrador de la suscripción, el portal crea una cuenta de ejecución para Resource Manager pero genera un error al implementar la cuenta de ejecución clásica. Si no desea admitir recursos clásicos, puede omitir este error.
>
> También puede crear una cuenta de ejecución con [PowerShell](https://docs.microsoft.com/azure/automation/manage-runas-account#create-run-as-account-using-powershell).

## <a name="next-steps"></a>Pasos siguientes

Aprenda cómo [incorporar sus servidores](./onboarding-overview.md) a los servicios de administración de servidores de Azure.

> [!div class="nextstepaction"]
> [Incorporación a los servicios de administración de servidores de Azure](./onboarding-overview.md)
