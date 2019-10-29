---
title: Línea base de administración mejorada en Azure
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: Mejoras comunes en la línea base de administración
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.custom: fasttrack-edit, AQC
ms.localizationpriority: high
ms.openlocfilehash: 85e289867ac69f3403d964078a7c3f3b2a6c96a7
ms.sourcegitcommit: f3371811a36e12533ecbc3aa936e2a68e0cee25f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2019
ms.locfileid: "72683693"
---
# <a name="enhanced-management-baseline-in-azure"></a>Línea base de administración mejorada en Azure

Las tres primeras disciplinas de administración en la nube describen una línea base de administración. En los artículos anteriores de esta guía se describe un producto mínimo viable (MVP) para servicios de administración en la nube, denominado "línea base de administración". En este artículo se describen algunas mejoras comunes de la línea base.

El propósito de una línea base de administración es crear una oferta coherente que proporcione un nivel mínimo de compromiso empresarial para **todas*** las cargas de trabajo compatibles. Esta línea base de ofertas de administración repetibles comunes permite al equipo ofrecer una administración operativa altamente optimizada con una desviación mínima. Sin embargo, podría ser necesario un mayor compromiso con la empresa más allá de la oferta estándar. La imagen y viñetas siguientes muestran tres maneras de ir más allá de la línea base de administración.

![Más allá de la línea base de administración en la nube](../../_images/manage/beyond-the-baseline.png)

- **Operaciones con cargas de trabajo:**
  - Mayor inversión por operaciones de carga de trabajo.
  - Mayor grado de resistencia.
  - Se sugiere para aproximadamente el 20 % de las cargas de trabajo que impulsan el valor empresarial.
  - Normalmente se reserva para cargas de trabajo de gran importancia o críticas.
- **Operaciones de la plataforma:**
  - La inversión en operaciones se reparte entre varias cargas de trabajo.
  - Las mejoras de resistencia afectan a todas las cargas de trabajo que usan la plataforma definida.
  - Se sugiere para aproximadamente el 20  % de las plataformas de importancia más alta.
  - Normalmente se reservan para cargas de trabajo de importancia media a importancia crítica.
- **Línea base de administración mejorada:**
  - Inversión más baja para operaciones relativas.
  - Se han mejorado ligeramente los compromisos empresariales mediante el uso de herramientas y procesos de operaciones nativos de la nube.

Ambas operaciones de carga de trabajo y plataforma requerirán cambios en los principios de diseño y arquitectura. Estos cambios pueden tardar un tiempo y generar mayores gastos de funcionamiento. Para reducir el número de cargas de trabajo que requieren tales inversiones, una línea base de administración mejorada podría proporcionar una mejora en el compromiso de negocio.

En la tabla siguiente se describen algunos procesos, herramientas y posibles impactos comunes en las líneas base de administración mejorada de los clientes.

|Materia  |Proceso  |Herramienta  |Posible impacto| Más información |
|---------|---------|---------|---------|---------|
|Inventario y visibilidad|Servicio Change Tracking|Azure Resource Graph|Una mayor visibilidad de los cambios en los servicios de Azure puede ayudar a detectar antes los impactos negativos o a remediarlos más rápido.|[Información general de Azure Resource Graph](https://docs.microsoft.com/azure/governance/resource-graph/overview)|
|Inventario y visibilidad|Integración de administración de servicios de TI (ITSM)|IT Service Management Connector|La conexión de ITSM automatizada crea reconocimiento más rápido.|[Conector ITSM de Azure](https://docs.microsoft.com/azure/azure-monitor/platform/itsmc-overview)|
|Cumplimiento operativo|Automatización de operaciones|Azure Automation|Automatiza el cumplimiento operativo para obtener una respuesta más rápida y precisa ante los cambios.|Consulte a continuación|
|Cumplimiento operativo|Operaciones de nube múltiple|Hybrid Runbook Worker de Azure Automation|Automatiza operaciones en varias nubes.|[Información general de Hybrid Runbook](https://docs.microsoft.com/azure/automation/automation-hybrid-runbook-worker)|
|Cumplimiento operativo|Automatización de invitados|Configuración de estado deseado (DSC)|Configuración basada en código de sistemas operativos invitados para reducir errores y el desfase de la configuración.|[Información general sobre DSC](/powershell/scripting/dsc/overview/overview)|
|Protección y recuperación|Notificación de infracción|Azure Security Center|Amplía la protección para incluir desencadenadores de recuperación ante infracciones de seguridad.|Consulte a continuación|

::: zone target="docs"

## <a name="azure-automation"></a>Azure Automation

::: zone-end
::: zone target="chromeless"

## <a name="azure-automationtabazureautomation"></a>[Azure Automation](#tab/AzureAutomation)

::: zone-end

Azure Automation proporciona un sistema centralizado para la administración de controles automatizados. En Azure Automation, los procesos de corrección, escala y optimización simples se pueden ejecutar en respuesta a las métricas del entorno, lo que reduce la sobrecarga asociada con el procesamiento manual de incidentes. Lo más importante es que la corrección automatizada se puede ofrecer casi en tiempo real, lo que reduce significativamente las interrupciones en los procesos empresariales. Un estudio de las interrupciones empresariales más comunes identificará las actividades que podrían automatizarse dentro de su entorno.

### <a name="runbooks"></a>Runbooks

La unidad básica de código para ofrecer corrección automatizada es un runbook. Los runbooks contienen las instrucciones para corregir o recuperarse de un incidente.

Para crear o administrar runbooks:

1. Vaya a [Azure Automation](https://portal.azure.com/#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.Automation%2FAutomationAccounts).
2. Elija una de las **cuentas de Automation** que se muestran.
3. Busque la sección **Automatización de procesos** de la navegación del portal.
4. Las opciones de esa sección permiten crear o administrar runbooks, programaciones y otras funcionalidades de corrección automatizadas.

::: zone target="chromeless"

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.Automation%2FAutomationAccounts]" submitText="Assign Policy" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end
::: zone target="docs"

## <a name="azure-security-center"></a>Azure Security Center

::: zone-end
::: zone target="chromeless"

## <a name="azure-security-centertabazuresecuritycenter"></a>[Azure Security Center](#tab/AzureSecurityCenter)

::: zone-end

Azure Security Center también desempeña un papel importante en su estrategia de protección y recuperación. Le permite supervisar la seguridad de las máquinas, las redes, el almacenamiento, los servicios de datos y las aplicaciones. Azure Security Center proporciona detección de amenazas avanzada mediante análisis del comportamiento y aprendizaje automático para ayudar a identificar las amenazas activas dirigidas a los recursos de Azure. También proporciona protección contra amenazas que bloquea el malware u otro código no deseado y reduce la superficie expuesta a los ataques por fuerza bruta y a otros ataques a la red.

Cuando Azure Security Center identifica una amenaza, desencadena una alerta de seguridad con los pasos que debe seguir para responder a un ataque. También proporciona un informe con datos sobre la amenaza detectada.

Azure Security Center se ofrece en dos niveles: gratis y estándar. Características como las recomendaciones de seguridad están disponibles en el nivel Gratis. El nivel estándar proporciona protección adicional, como detección de amenazas avanzada y protección en las cargas de trabajo de nube híbrida.

::: zone target="chromeless"

### <a name="action"></a>.

**Pruebe el nivel estándar gratis durante los primeros 30 días.**

Después de habilitar y configurar las directivas de seguridad para los recursos de una suscripción, puede ver el estado de seguridad de los recursos y cualquier problema en la sección **Prevención**. Una lista de dichos problemas también se puede encontrar en el icono **Recomendaciones**.

::: form action="OpenBlade[#blade/Microsoft_Azure_Security/SecurityMenuBlade/SecurityMenuBlade/0]" submitText="Explore Azure Security Center" :::

::: zone-end

::: zone target="docs"

Para explorar Azure Security Center, vaya a [Azure Portal](https://portal.azure.com/#blade/Microsoft_Azure_Security/SecurityMenuBlade/SecurityMenuBlade/0).

### <a name="learn-more"></a>Más información

Para más información, consulte la [documentación de Azure Security Center](https://docs.microsoft.com/azure/security-center).

::: zone-end
