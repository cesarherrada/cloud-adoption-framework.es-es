---
title: Línea base de administración mejorada en Azure
description: Mejoras comunes en la línea base de administración
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.custom: fasttrack-edit, AQC
ms.localizationpriority: high
ms.openlocfilehash: ad40011769152d906481fe8ffba5dead3f6b0ae5
ms.sourcegitcommit: 2362fb3154a91aa421224ffdb2cc632d982b129b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76808250"
---
# <a name="enhanced-management-baseline-in-azure"></a>Línea base de administración mejorada en Azure

Las tres primeras materias de administración de la nube describen una línea de base de administración. En los artículos anteriores de esta guía se describe un producto mínimo viable (MVP) para servicios de administración en la nube, lo que se conoce como "línea de referencia de administración". En este artículo se describen algunas mejoras comunes de la línea base.

El propósito de una línea de referencia de administración es crear una oferta coherente que proporcione un nivel mínimo de compromiso empresarial para *todas* las cargas de trabajo que se admiten. Con esta línea de referencia de ofertas de administración repetibles comunes, el equipo puede ofrecer una administración operativa altamente optimizada con una desviación mínima.

Sin embargo, podría ser necesario un mayor compromiso con la empresa más allá de la oferta estándar. La imagen y la lista siguientes muestran tres maneras de ir más allá de la base de referencia de administración.

![Más allá de la línea base de administración en la nube](../../_images/manage/beyond-the-baseline.png)

- **Operaciones con cargas de trabajo:**
  - Mayor inversión por operaciones de carga de trabajo.
  - Mayor grado de resistencia.
  - Se sugiere para aproximadamente el 20 % de las cargas de trabajo que impulsan el valor empresarial.
  - Normalmente se reserva para cargas de trabajo de gran importancia o críticas.
- **Operaciones de la plataforma:**
  - La inversión en operaciones se reparte entre varias cargas de trabajo.
  - Las mejoras de resistencia afectan a todas las cargas de trabajo que usan la plataforma definida.
  - Se sugieren para aproximadamente el 20 % de las plataformas que tienen una importancia crítica.
  - Normalmente se reservan para cargas de trabajo de importancia media a importancia crítica.
- **Línea de base de administración mejorada:**
  - Inversión más baja para operaciones relativas.
  - Se han mejorado ligeramente los compromisos empresariales mediante herramientas y procesos de operaciones nativos de la nube.

Ambas operaciones de carga de trabajo y plataforma requieren cambios en los principios de diseño y arquitectura. Estos cambios pueden tardar un tiempo y generar mayores gastos de funcionamiento. Para reducir el número de cargas de trabajo que requieren tales inversiones, una base de referencia de administración mejorada puede proporcionar una mejora suficiente en el compromiso empresarial.

En esta tabla se describen algunos procesos, herramientas y posibles consecuencias comunes en las bases de referencia de administración mejorada de los clientes:

| Materia  | Proceso  | Herramienta | Posible impacto | Más información |
|---|---|---|---|---|
|Inventario y visibilidad|Servicio Change Tracking|Azure Resource Graph|Una mayor visibilidad de los cambios en los servicios de Azure puede ayudar a detectar antes los efectos negativos o a remediarlos más rápido.|[Información general de Azure Resource Graph](https://docs.microsoft.com/azure/governance/resource-graph/overview)|
|Inventario y visibilidad|Integración de Administración de servicios de TI (ITSM)|IT Service Management Connector|La conexión de ITSM automatizada crea reconocimiento más rápido.|[Conector de Administración de servicios de TI (ITSMC)](https://docs.microsoft.com/azure/azure-monitor/platform/itsmc-overview)|
|Cumplimiento operativo|Automatización de operaciones|Azure Automation|Automatiza el cumplimiento operativo para obtener una respuesta más rápida y precisa ante los cambios.|Consulte las secciones siguientes|
|Cumplimiento operativo|Operaciones de nube múltiple|Hybrid Runbook Worker de Azure Automation|Automatiza operaciones en varias nubes.|[Introducción a Hybrid Runbook Worker](https://docs.microsoft.com/azure/automation/automation-hybrid-runbook-worker)|
|Cumplimiento operativo|Automatización de invitados| Configuración de estado deseado (DSC)|Configuración basada en código de sistemas operativos invitados para reducir los errores y el desfase de la configuración.|[Información general sobre DSC](https://docs.microsoft.com/powershell/scripting/dsc/overview/overview)|
|Protección y recuperación|Notificación de infracción|Azure Security Center|Amplía la protección para incluir desencadenadores de recuperación ante infracciones de seguridad.|Consulte las secciones siguientes|

::: zone target="docs"

## <a name="azure-automation"></a>Azure Automation

::: zone-end
::: zone target="chromeless"

## <a name="azure-automationtabazureautomation"></a>[Azure Automation](#tab/AzureAutomation)

::: zone-end

Azure Automation proporciona un sistema centralizado para la administración de controles automatizados. En Azure Automation, puede ejecutar procesos de corrección, escala y optimización simples en respuesta a las métricas del entorno. Estos procesos reducen la sobrecarga asociada con el procesamiento manual de incidentes.

Lo más importante es que la corrección automatizada se puede ofrecer casi en tiempo real, lo que reduce significativamente las interrupciones en los procesos empresariales. Un estudio de las interrupciones empresariales más comunes identifica las actividades que podrían automatizarse dentro de su entorno.

### <a name="runbooks"></a>Runbooks

La unidad básica de código para ofrecer corrección automatizada es un runbook. Los runbooks contienen las instrucciones para corregir o recuperarse de un incidente.

Para crear o administrar runbooks:

1. Vaya a [Azure Automation](https://portal.azure.com/#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.Automation%2FAutomationAccounts).
1. Seleccione **Cuentas de Automation** y elija una de las cuentas de la lista.
1. Diríjase a **Automatización de procesos**.
1. Con las opciones presentadas, puede crear o administrar runbooks, programaciones y otras funcionalidades de corrección automatizadas.

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

Azure Security Center también desempeña un papel importante en su estrategia de protección y recuperación. Le permite supervisar la seguridad de las máquinas, las redes, el almacenamiento, los servicios de datos y las aplicaciones.

Azure Security Center proporciona detección de amenazas avanzada mediante análisis del comportamiento y aprendizaje automático para ayudar a identificar las amenazas activas dirigidas a los recursos de Azure. También proporciona protección contra amenazas, que bloquea el malware y otro código no deseado, y reduce la superficie expuesta a los ataques por fuerza bruta y a otros ataques a la red.

Cuando Azure Security Center identifica una amenaza, desencadena una alerta de seguridad con los pasos que debe seguir para responder a un ataque. También proporciona un informe con datos sobre la amenaza detectada.

Azure Security Center se ofrece en dos niveles: Gratis y Estándar. Características como las recomendaciones de seguridad están disponibles en el nivel Gratis. El nivel Estándar proporciona protección adicional, como detección de amenazas avanzada y protección en las cargas de trabajo de nube híbrida.

::: zone target="chromeless"

### <a name="action"></a>Acción

#### <a name="try-standard-tier-for-free-for-your-first-30-days"></a>Probar el nivel Estándar gratis durante los primeros 30 días

Después de habilitar y configurar las directivas de seguridad para los recursos de una suscripción, puede ver el estado de seguridad de los recursos y cualquier problema en el panel **Prevención**. Una lista de dichos problemas también se puede encontrar en el icono **Recomendaciones**.

::: form action="OpenBlade[#blade/Microsoft_Azure_Security/SecurityMenuBlade/SecurityMenuBlade/0]" submitText="Explore Azure Security Center" :::

::: zone-end

::: zone target="docs"

Para explorar Azure Security Center, vaya a [Azure Portal](https://portal.azure.com/#blade/Microsoft_Azure_Security/SecurityMenuBlade/SecurityMenuBlade/0).

### <a name="learn-more"></a>Más información

Para más información, consulte la [documentación de Azure Security Center](https://docs.microsoft.com/azure/security-center).

::: zone-end
