---
title: Especialización de la carga de trabajo para la administración en la nube en Azure
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: Mejore las operaciones de administración en la nube específicas de la carga de trabajo
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.custom: fasttrack-edit, AQC
ms.localizationpriority: high
ms.openlocfilehash: 51bdf23ccb2262202dfa095c5e9b57f727d11d3b
ms.sourcegitcommit: 35c162d2d09ec1c4a57d3d57a5db1d56ee883806
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72556996"
---
# <a name="workload-specialization-for-cloud-management"></a>Especialización de la carga de trabajo para la administración en la nube

La especialización de la carga de trabajo se basa en los conceptos que se describen en [Especialización de la plataforma](./platform-specialization.md).

![Más allá de la línea base de administración en la nube](../../_images/manage/beyond-the-baseline.png)

- **Operaciones con cargas de trabajo:** Mayor inversión por operaciones de carga de trabajo. Mayor grado de resistencia. Se sugiere para alrededor del 20 % de las cargas de trabajo que impulsan el valor empresarial. Suele reservase para cargas de trabajo de gran importancia o críticas.
- **Operaciones de la plataforma:** La inversión en operaciones se reparte entre varias cargas de trabajo. Las mejoras de resistencia afectan a todas las cargas de trabajo que aprovechan la plataforma definida. Se sugiere para aproximadamente el 20  % de las plataformas de importancia más alta. Se suelen reservar para cargas de trabajo de importancia media a crítica.
- **Línea de base de administración mejorada:** Inversión más baja para operaciones relativas. Se han mejorado ligeramente los compromisos empresariales mediante herramientas y procesos de operaciones nativos de la nube.

## <a name="high-level-process"></a>Proceso de alto nivel

La especialización de la carga de trabajo consta de una ejecución disciplinada de los cuatro procesos siguientes con un enfoque iterativo. Cada proceso se explica con más detalle en el artículo [Especialización de la plataforma](./platform-specialization.md).

- **Mejora del diseño del sistema:** se mejora el diseño de una carga de trabajo específica para minimizar las interrupciones de forma eficaz.
- **Corrección automática:** algunas mejoras no son rentables. En tales casos, es posible que tenga más sentido automatizar la corrección y reducir el impacto de las interrupciones.
- **Escalado de la solución:** a medida que se mejoran el diseño de sistemas y la corrección automatizada, los cambios se pueden escalar en el entorno a través del catálogo de servicios.
- **Mejora continua:** se pueden usar varias herramientas de supervisión para detectar mejoras incrementales que se pueden llevar a cabo en el siguiente paso del diseño del sistema, la automatización y la escala.

## <a name="cultural-change"></a>Cambio cultural

La especialización de carga de trabajo suele desencadenar un cambio en la cultura. La TI tradicional crea procesos que se centran en ofrecer una línea de base de administración, líneas de base mejoradas y operaciones de plataforma. Estos tipos de ofertas se pueden escalar en todo el entorno. La especialización de la carga de trabajo es muy similar en aplicación a la especialización de plataforma. Sin embargo, a diferencia de las plataformas comunes, la especialización que requieren las cargas de trabajo individuales no suele escalarse.

Cuando se requiere la especialización de carga de trabajo, es habitual que la administración operativa evolucione más allá de una perspectiva de TI central. El enfoque sugerido en la Plataforma de adopción de la nube es una distribución de la funcionalidad de administración en la nube.

En este modelo, las tareas operativas como la supervisión, la implementación, DevOps y otras funciones centradas en la innovación se desplazan a una organización de desarrollo de aplicaciones o de unidad de negocio. La Plataforma en la nube y el equipo de supervisión de la nube principal todavía cumplen con la línea de base de administración en todo el entorno. Esos equipos centralizados también guían e instruyen a los equipos especializados en cargas de trabajo sobre las operaciones de sus cargas de trabajo. Sin embargo, la responsabilidad operativa cotidiana recae en un equipo de administración en la nube que se administra fuera de TI. Este tipo de control distribuido es uno de los indicadores principales de madurez del Centro de excelencia de la nube.

## <a name="beyond-platform-specialization---application-insights"></a>Más allá de la especialización de plataforma: Application Insights

Se requieren más detalles sobre la carga de trabajo específica para proporcionar operaciones de carga de trabajo claras. Durante la fase de mejora continua, Application Insights será una adición necesaria a la cadena de herramientas de administración en la nube.

|Supervisión de aplicaciones|Application Insights|Supervisión y diagnóstico de aplicaciones| |Rendimiento, disponibilidad y uso|Application Insights|Supervisión avanzada de aplicaciones con el panel de aplicaciones, mapas compuestos, uso y trazas|

### <a name="deploy-application-insights"></a>Implementar Application Insights

1. En Azure Portal, busque **Application Insights**.
2. Haga clic en **+ Agregar** para crear un recurso de Use Application Insights para supervisar la aplicación web en vivo.
3. Siga las instrucciones que aparecen en pantalla.

Para obtener instrucciones sobre cómo configurar la aplicación para la supervisión, consulte el [centro sobre Application Insights de Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/azure-monitor-app-hub).

::: zone target="chromeless"

::: form action="OpenBlade[#create/Microsoft.AppInsights]" submitText="Create Application Insight resources" :::

::: zone-end

### <a name="monitor-performance-availability-and-usage"></a>Supervisión del rendimiento, la disponibilidad y el uso

1. En Azure Portal, busque **Application Insights**.
2. Elija uno de los recursos de Application Insights de la lista.

La navegación de Application Insights contiene diversas opciones para supervisar el rendimiento, la disponibilidad, el uso y las dependencias. Cada una de estas vistas de los datos de la aplicación le aportará más claridad sobre el ciclo de comentarios para la mejora continua.

::: zone target="chromeless"

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/microsoft.insights%2Fcomponents]" submitText="Monitor applications" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end
