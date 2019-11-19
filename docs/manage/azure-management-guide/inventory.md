---
title: Inventario y visibilidad en Azure
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: Aprenda a configurar el inventario, la supervisión, los informes y las alertas para el entorno de administración de Azure.
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.custom: fasttrack-edit, AQC
ms.localizationpriority: high
ms.openlocfilehash: 84efac562647d88235dbcecbb2078e632c1c0341
ms.sourcegitcommit: bf9be7f2fe4851d83cdf3e083c7c25bd7e144c20
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73565459"
---
# <a name="inventory-and-visibility-in-azure"></a>Inventario y visibilidad en Azure

El _Inventario y la visibilidad_ es la primera de tres disciplinas en una línea de base para la administración en la nube.

![Línea de referencia de administración en la nube](../../_images/manage/management-baseline.png)

Esta materia va en primer lugar porque es fundamental recopilar los datos operativos adecuados al tomar decisiones sobre las operaciones. Los equipos de administración en la nube deben comprender lo que se está administrando y el grado de funcionamiento de esos recursos. En este artículo se describen las diversas herramientas que proporcionan un inventario y permiten ver el estado de ejecución del inventario.

Para cualquier entorno de nivel empresarial, en la tabla siguiente se describen los mínimos sugeridos para una línea de referencia de administración.

|Proceso  |Herramienta  |Propósito  |
|---------|---------|---------|
|Supervisión del estado de los servicios de Azure|Azure Service Health|Mantenimiento, rendimiento y diagnóstico de los servicios que se ejecutan en Azure|
|Centralización de registros|Log Analytics|Registro central para todos los fines de visibilidad|
|Centralización de la supervisión|Azure Monitor|Supervisión central de los datos operativos y las tendencias|
|Inventario de máquina virtual y Change Tracking|Azure Change Tracking e Inventario|Inventario de máquinas virtuales y supervisión de cambios para el nivel de SO invitado|
|Estado del servicio|Azure Activity Log|Supervisión de los cambios en el nivel de suscripción|
|Supervisión del sistema operativo invitado|Azure Monitor para máquinas virtuales|Supervisión de los cambios y el rendimiento de las VM|
|Supervisión de redes|Azure Network Watcher|Supervisión de los cambios y el rendimiento de la red|
|Supervisión de DNS|DNS Analytics|Seguridad, rendimiento y operaciones de DNS|

::: zone target="docs"

## <a name="azure-service-health"></a>Azure Service Health

::: zone-end
::: zone target="chromeless"

## <a name="azure-service-healthtabazureservicehealth"></a>[Azure Service Health](#tab/AzureServiceHealth)

::: zone-end

Azure Service Health proporciona una vista personalizada del estado de los servicios y regiones de Azure. La información acerca de los problemas activos se publica en Service Health, lo cual le ayudará a comprender el efecto que tienen en los recursos. Las actualizaciones periódicas le mantendrán informado a medida que se resuelven los problemas.

También se publican los eventos de mantenimiento planeado en Service Health para proporcionarle información sobre los cambios que pueden afectar a la disponibilidad de los recursos. Configure alertas de Service Health para que le envíen notificaciones si se producen problemas en el servicio, mantenimientos planeados o cualquier otro cambio que puedan afectar a los servicios y regiones de Azure.

Azure Service Health incluye:

- **Estado de Azure:** una vista global del estado de los servicios de Azure.
- **Estado del servicio:** una vista personalizada del estado de los servicios de Azure.
- **Estado de los recursos:** una vista más detallada del estado de los recursos individuales.

::: zone target="chromeless"

<!-- markdownlint-disable MD024 -->

### <a name="action"></a>.

Para configurar una alerta de Service Health:

1. Vaya a **Service Health**.
2. Seleccione **Alertas de estado**.
3. Cree una alerta de estado del servicio.

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/Microsoft_Azure_Health/AzureHealthBrowseBlade/healthalerts]" submitText="Go to Service Health" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

::: zone target="docs"

Para configurar una alerta de Service Health, vaya a [Azure Portal](https://portal.azure.com/#blade/Microsoft_Azure_Health/AzureHealthBrowseBlade/healthalerts).

### <a name="learn-more"></a>Más información

Para más información, consulte la [documentación de Azure Service Health](https://docs.microsoft.com/azure/service-health).

## <a name="log-analytics"></a>Log Analytics

::: zone-end
::: zone target="chromeless"

## <a name="log-analyticstablog-analytics"></a>[Log Analytics](#tab/Log-Analytics)

::: zone-end

Un [área de trabajo de Log Analytics](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) es un entorno único para almacenar los datos de registro de Azure Monitor. Cada área de trabajo tiene su propio repositorio y configuración de datos. Los orígenes de datos y las soluciones se configuran para almacenar sus datos en áreas de trabajo determinadas. Las soluciones de supervisión de Azure requieren que todos los servidores se conecten a un área de trabajo, para poder almacenar los datos de registro y obtener acceso a ellos.

::: zone target="chromeless"

### <a name="action"></a>.

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.OperationalInsights%2Fworkspaces]" submitText="Explore Azure Monitor" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

::: zone target="docs"

### <a name="learn-more"></a>Más información

Para obtener más información, consulte la [documentación para la creación de áreas de trabajo de Log Analytics](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace).

## <a name="azure-monitor"></a>Azure Monitor

::: zone-end
::: zone target="chromeless"

## <a name="azure-monitortabazure-monitor"></a>[Azure Monitor](#tab/Azure-Monitor)

::: zone-end

Azure Monitor proporciona un único centro unificado para todos los datos de supervisión y diagnóstico en Azure, además de ofrecer visibilidad sobre todos los recursos. Con Azure Monitor, puede buscar y corregir problemas y optimizar el rendimiento. También puede comprender el comportamiento de los clientes.

- **Supervise y visualice las métricas:** las métricas son valores numéricos disponibles en los recursos de Azure. Ayudan a comprender el estado de los sistemas. Personalice los gráficos de los paneles y use los libros para los informes.

- **Consulte y analice los registros:** los registros incluyen los registros de actividad y los registros de diagnóstico de Azure. Recopile registros adicionales de otras soluciones de supervisión y administración para los recursos de nube o locales. Log Analytics proporciona un repositorio central para agregar todos estos datos. Desde allí, puede ejecutar consultas para ayudar a solucionar problemas o para visualizar los datos.

- **Configure alertas y acciones:** las alertas le notifican las condiciones críticas. Las acciones correctivas se pueden tomar basándose en los desencadenadores de las métricas, los registros o los problemas de estado del servicio. Puede configurar diferentes notificaciones y acciones, así como enviar datos a las herramientas de administración de servicios de TI.

::: zone target="chromeless"

### <a name="action"></a>.

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/Microsoft_Azure_Monitoring/AzureMonitoringBrowseBlade/overview]" submitText="Explore Azure Monitor" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

::: zone target="docs"

 Comience a supervisar lo siguiente:

- [Aplicaciones](https://docs.microsoft.com/azure/application-insights/app-insights-overview)
- [Contenedores](https://docs.microsoft.com/azure/monitoring/monitoring-container-overview)
- [Máquinas virtuales](https://docs.microsoft.com/azure/monitoring/monitoring-service-map)
- [Redes](https://docs.microsoft.com/azure/networking/network-monitoring-overview)

Para supervisar otros recursos, busque soluciones adicionales en Azure Marketplace.

Para explorar Azure Monitor, vaya a [Azure Portal](https://portal.azure.com/#blade/Microsoft_Azure_Monitoring/AzureMonitoringBrowseBlade/overview).

### <a name="learn-more"></a>Más información

Para más información, consulte [Documentación sobre Azure Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics).

## <a name="onboard-solutions"></a>Incorporación de soluciones

::: zone-end
::: zone target="chromeless"

## <a name="onboard-solutionstabconfigure-solutions"></a>[Incorporación de soluciones](#tab/Configure-solutions)

::: zone-end

Para habilitar las soluciones, tiene que configurar el área de trabajo Log Analytics. Las VM de Azure y los servidores locales incorporados obtienen las soluciones de las áreas de trabajo de Log Analytics a las que se conectan.

Hay dos enfoques en la incorporación:

- [Una única máquina virtual](https://docs.microsoft.com/azure/cloud-adoption-framework/manage/azure-server-management/onboard-single-vm)
- [Toda la suscripción](https://docs.microsoft.com/azure/cloud-adoption-framework/manage/azure-server-management/onboard-at-scale)

Cada uno de los artículos le guía a través de una serie de pasos para incorporar las siguientes soluciones:

- Administración de actualizaciones
- Change Tracking e Inventario
- Azure Activity Log
- Agent Health para Azure Log Analytics
- Evaluación antimalware
- Azure Monitor para máquinas virtuales
- Azure Security Center

Cada uno de los pasos anteriores ayuda a establecer el inventario y la visibilidad.
