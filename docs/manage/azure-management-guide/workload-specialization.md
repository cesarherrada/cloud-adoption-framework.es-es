---
title: Especialización de la carga de trabajo para la administración en la nube en Azure
description: Mejore las operaciones de administración en la nube específicas de la carga de trabajo
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.custom: fasttrack-edit, AQC
ms.localizationpriority: high
ms.openlocfilehash: ee41e95a8481cd7caeb91d05d4b1420e357aa0f5
ms.sourcegitcommit: 2362fb3154a91aa421224ffdb2cc632d982b129b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76808148"
---
# <a name="workload-specialization-for-cloud-management"></a>Especialización de la carga de trabajo para la administración en la nube

La especialización de la carga de trabajo se basa en los conceptos que se describen en [Especialización de la plataforma](./platform-specialization.md).

![Más allá de la línea base de administración en la nube](../../_images/manage/beyond-the-baseline.png)

- **Operaciones con cargas de trabajo:** mayor inversión en operaciones por carga de trabajo y mayor grado de resistencia. Las operaciones con cargas de trabajo se sugieren para aproximadamente el 20 % de las cargas de trabajo que impulsan el valor empresarial. Esta especialización suele reservarse para cargas de trabajo de gran importancia o críticas.
- **Operaciones de la plataforma:** La inversión en operaciones se reparte entre varias cargas de trabajo. Las mejoras de resistencia afectan a todas las cargas de trabajo que usan la plataforma definida. Las operaciones de la plataforma se sugieren para aproximadamente el 20 % de las plataformas que tienen una importancia crítica. Esta especialización se suele reservar para cargas de trabajo de importancia media a crítica.
- **Línea de base de administración mejorada:** inversión en operaciones relativamente más baja. Esta especialización mejora ligeramente los compromisos empresariales mediante herramientas y procesos de operaciones nativos de la nube.

## <a name="high-level-process"></a>Proceso de alto nivel

La especialización de la carga de trabajo consta de una ejecución disciplinada de los cuatro procesos siguientes con un enfoque iterativo. Cada proceso se explica con más detalle en [Especialización de la plataforma](./platform-specialization.md).

- **Mejora del diseño del sistema:** se mejora el diseño de una carga de trabajo específica para minimizar las interrupciones de forma eficaz.
- **Corrección automática:** algunas mejoras no son rentables. En tales casos, es posible que tenga más sentido automatizar la corrección y reducir el efecto de las interrupciones.
- **Escalado de la solución:** a medida mejora el diseño de los sistemas y la corrección automatizada, los cambios se pueden escalar en el entorno mediante el catálogo de servicios.
- **Mejora continua:** puede usar distintas herramientas de supervisión para detectar mejoras incrementales. Estas mejoras se pueden tratar en el siguiente paso del diseño, la automatización y la escala del sistema.

## <a name="cultural-change"></a>Cambio cultural

La especialización de la carga de trabajo suele desencadenar un cambio cultural en los procesos de compilación de TI tradicionales que se centran en ofrecer una base de referencia de administración, bases de referencia mejoradas y operaciones de plataforma. Estos tipos de ofertas se pueden escalar en todo el entorno. La especialización de la carga de trabajo es similar en aplicación a la especialización de plataforma. Sin embargo, a diferencia de las plataformas comunes, la especialización que requieren las cargas de trabajo individuales no suele escalarse.

Cuando se requiere la especialización de carga de trabajo, la administración operativa suele evolucionar más allá de una perspectiva de TI central. El enfoque sugerido de Cloud Adoption Framework es una distribución de la funcionalidad de administración en la nube.

En este modelo, las tareas operativas como la supervisión, la implementación, DevOps y otras funciones centradas en la innovación se desplazan a una organización de desarrollo de aplicaciones o de unidad de negocio. La Plataforma en la nube y el equipo de supervisión de la nube principal todavía cumplen con la línea de base de administración en todo el entorno.

Esos equipos centralizados también guían e instruyen a los equipos especializados en cargas de trabajo sobre las operaciones de sus cargas de trabajo. Sin embargo, la responsabilidad operativa cotidiana recae en un equipo de administración en la nube que se administra fuera de TI. Este tipo de control distribuido es uno de los indicadores principales de madurez del centro de excelencia de la nube.

## <a name="beyond-platform-specialization-application-insights"></a>Más allá de la especialización de la plataforma: Application Insights

Se requieren más detalles sobre la carga de trabajo específica para proporcionar operaciones de carga de trabajo claras. Durante la fase de mejora continua, Application Insights será una adición necesaria a la cadena de herramientas de administración en la nube.

|Requisito|Herramienta|Propósito|
|---|---|---|
|Supervisión de aplicaciones|Application Insights|Supervisión y diagnóstico de aplicaciones|
|Rendimiento, disponibilidad y uso|Application Insights|Supervisión avanzada de aplicaciones mediante paneles de aplicaciones, mapas compuestos, uso y seguimiento|

### <a name="deploy-application-insights"></a>Implementar Application Insights

1. En Azure Portal, diríjase a **Application Insights**.
1. Haga clic en **+ Agregar** para crear un recurso de Application Insights y supervisar la aplicación web en vivo.
1. Siga las instrucciones que aparecen en pantalla.

Para obtener instrucciones sobre cómo configurar la aplicación para la supervisión, consulte el [centro sobre Application Insights de Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/azure-monitor-app-hub).

::: zone target="chromeless"

::: form action="OpenBlade[#create/Microsoft.AppInsights]" submitText="Create Application Insight resources" :::

::: zone-end

### <a name="monitor-performance-availability-and-usage"></a>Supervisión del rendimiento, la disponibilidad y el uso

1. En Azure Portal, busque **Application Insights**.
1. Elija uno de los recursos de Application Insights de la lista.

Application Insights contiene diversos tipos de opciones para supervisar el rendimiento, la disponibilidad, el uso y las dependencias. Cada una de estas vistas de los datos de la aplicación proporciona más claridad sobre el ciclo de comentarios para la mejora continua.

::: zone target="chromeless"

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/microsoft.insights%2Fcomponents]" submitText="Monitor applications" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end
