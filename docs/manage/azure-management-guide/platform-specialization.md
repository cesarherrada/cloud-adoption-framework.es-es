---
title: Especialización de la plataforma para la administración en la nube en Azure
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: Mejore las operaciones de administración en la nube específicas de la plataforma.
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.custom: fasttrack-edit, AQC
ms.localizationpriority: high
ms.openlocfilehash: 0386a8c30758cce6c1c3d23bfa73d1f90e919692
ms.sourcegitcommit: 35c162d2d09ec1c4a57d3d57a5db1d56ee883806
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72556979"
---
# <a name="platform-specialization-for-cloud-management"></a>Especialización de la plataforma para la administración en la nube

Al igual que la línea de base de administración mejorada, la especialización de plataforma es una extensión más allá de la línea de base de administración estándar. A continuación se muestra una lista con viñetas visual de las formas de expandir la línea base de administración. En este artículo se trata la opción de especialización de plataforma.

![Más allá de la línea base de administración en la nube](../../_images/manage/beyond-the-baseline.png)

- **Operaciones con cargas de trabajo:** Mayor inversión por operaciones de carga de trabajo. Mayor grado de resistencia. Se sugiere para alrededor del 20 % de las cargas de trabajo que impulsan el valor empresarial. Suele reservase para cargas de trabajo de gran importancia o críticas.
- **Operaciones de la plataforma:** La inversión en operaciones se reparte entre varias cargas de trabajo. Las mejoras de resistencia afectan a todas las cargas de trabajo que aprovechan la plataforma definida. Se sugiere para aproximadamente el 20  % de las plataformas de importancia más alta. Se suelen reservar para cargas de trabajo de importancia media a crítica.
- **Línea de base de administración mejorada:** Inversión más baja para operaciones relativas. Se han mejorado ligeramente los compromisos empresariales mediante herramientas y procesos de operaciones nativos de la nube.

Ambas operaciones de carga de trabajo y plataforma requerirán cambios en los principios de diseño y arquitectura. Estos cambios pueden tardar un tiempo y generar mayores gastos de funcionamiento. Para reducir el número de cargas de trabajo que requieren tales inversiones, una línea base de administración mejorada podría proporcionar una mejora en el compromiso de negocio.

En la tabla siguiente se describen algunos procesos, herramientas y posibles consecuencias comunes en las líneas base de administración mejorada de los clientes.

|Proceso  |Herramienta  |Propósito  |Nivel de administración sugerido  |
|---------|---------|---------|---------|
|Mejora del diseño del sistema|Marco de arquitectura de Azure|Mejora del diseño arquitectónico de la plataforma para mejorar las operaciones|
|Corrección automática|Azure Automation|Respuesta a datos avanzados de la plataforma con automatización específica de la plataforma|Operaciones de la plataforma|
|Catálogo de servicios|Centro de Managed Applications|Catálogo de autoservicio de soluciones aprobadas que cumplen los estándares de la organización|Operaciones de la plataforma|
|Rendimiento de contenedores|Azure Monitor para contenedores|Supervisión y diagnóstico de contenedores|Operaciones de la plataforma|
|Rendimiento de datos de PaaS|Azure SQL Analytics|Supervisión y diagnóstico de bases de datos de PaaS|Operaciones de la plataforma|
|Rendimiento de datos de IaaS|Comprobación de estado de SQL Server|Supervisión y diagnóstico de bases de datos de IaaS|Operaciones de la plataforma|

## <a name="high-level-process"></a>Proceso de alto nivel

La especialización de la plataforma consta de una ejecución disciplinada de los cuatro procesos siguientes con un enfoque iterativo. Cada proceso se explica con más detalle en las siguientes secciones del artículo.

- **Mejora del diseño del sistema:** se mejora el diseño de sistemas comunes (o plataformas) para minimizar las interrupciones de forma eficaz.
- **Corrección automática:** algunas mejoras no son rentables. En tales casos, es posible que tenga más sentido automatizar la corrección y reducir el impacto de las interrupciones.
- **Escalado de la solución:** a medida que se mejoran el diseño de sistemas y la corrección automatizada, los cambios se pueden escalar en el entorno a través del catálogo de servicios.
- **Mejora continua:** se pueden usar varias herramientas de supervisión para detectar mejoras incrementales que se pueden llevar a cabo en el siguiente paso del diseño del sistema, la automatización y la escala.

::: zone target="docs"

## <a name="improve-system-design"></a>Mejora del diseño del sistema

::: zone-end
::: zone target="chromeless"

## <a name="improve-system-designtabsystemsdesign"></a>[Mejora del diseño del sistema](#tab/SystemsDesign)

::: zone-end

La mejora del diseño del sistema es el enfoque más eficaz para mejorar las operaciones de cualquier plataforma común.Gracias a las mejoras en el diseño del sistema, la estabilidad puede aumentar y las interrupciones del negocio pueden disminuir. Through system design improvements, stability can increase and business interruptions can decrease. El diseño de sistemas individuales está fuera del ámbito de la perspectiva adoptada la vista en toda la plataforma de adopción de la nube. Como complemento de esta plataforma, el marco de arquitectura de Azure proporciona procedimientos recomendados para mejorar la resistencia y el diseño de un sistema específico. Estas mejoras de diseño se pueden aplicar al diseño de sistemas de una plataforma o una carga de trabajo específicas.

El marco de arquitectura de Azure se centra en la mejora de cinco pilares del diseño de sistemas:

- **Escalabilidad:** escalado de los recursos comunes de la plataforma para controlar el aumento de la carga.
- **Disponibilidad:** disminución de las interrupciones empresariales al mejorar el tiempo de actividad potencial.
- **Resistencia:** mejora de los tiempos de recuperación para reducir la duración de las interrupciones.
- **Seguridad:** protección de las aplicaciones y los datos frente a amenazas externas.
- **Administración:** procesos operativos específicos de los recursos comunes de la plataforma.

La mayoría de las interrupciones empresariales son resultado de alguna forma de deuda técnica o deficiencia en la arquitectura. En el caso de las implementaciones existentes, las mejoras en el diseño de los sistemas pueden verse como pagos de la deuda técnica existente. En el caso de las implementaciones nuevas, las mejoras en el diseño de los sistemas pueden verse como evasión de la deuda técnica. La siguiente pestaña, "Corrección automatizada", examina las formas de abordar la deuda técnica que no se puede o no se debe solucionar.

Obtenga más información acerca del [marco de arquitectura de Azure](https://docs.microsoft.com/azure/architecture/guide/pillars) para mejorar el diseño del sistema.

A medida que el diseño del sistema mejora, vuelva a consultar este artículo para encontrar nuevas oportunidades de mejorar y escalar dichas mejoras en todo el entorno.

::: zone target="docs"

## <a name="automated-remediation"></a>Corrección automatizada

::: zone-end
::: zone target="chromeless"

## <a name="automated-remediationtabautomatedremediation"></a>[Corrección automatizada](#tab/AutomatedRemediation)

::: zone-end

Algunas deudas técnicas no se pueden abordar, ya que la resolución podría resultar demasiado costosa para corregirla. La resolución se puede planear, pero tiene una larga duración de proyecto. Podría deberse a que la interrupción del negocio no tiene un efecto importante en la empresa o a que la prioridad empresarial es recuperarse rápidamente en lugar de invertir en resistencia.

Cuando la ruta deseada no es la resolución de la deuda técnica, la corrección automática suele ser el siguiente paso deseado. El uso de Azure Automation y Azure Monitor para detectar tendencias y proporcionar una corrección automatizada es el enfoque más común para la corrección automatizada.

Para obtener instrucciones sobre la corrección automatizada, consulte este artículo en [Azure Automation y alertas](https://docs.microsoft.com/azure/automation/automation-create-alert-triggered-runbook).

::: zone target="docs"

## <a name="scale-the-solution-with-a-service-catalog"></a>Escalado de la solución con un catálogo de servicios

::: zone-end
::: zone target="chromeless"

## <a name="scale-the-solution-with-a-service-catalogtabservicecatalog"></a>[Escalado de la solución con un catálogo de servicios](#tab/ServiceCatalog)

::: zone-end

La piedra angular de las operaciones de plataforma y la especialización de plataforma es un catálogo de servicios bien administrado. A través de él se escalan las mejoras en el diseño del sistema y las correcciones en un entorno. El equipo de plataforma en la nube y el equipo de automatización en la nube se coordinan para crear soluciones repetibles para las plataformas más comunes en cualquier entorno. Sin embargo, si esas soluciones no se aprovechan de forma coherente, la administración en la nube puede proporcionar poco más que una oferta de línea de base.

Para maximizar la adopción y minimizar la sobrecarga de mantenimiento de cualquier plataforma optimizada, dicha plataforma se debe agregar a un catálogo de servicios dentro de Azure. Todas las aplicaciones del catálogo se pueden implementar para consumo interno a través del catálogo de servicios o como una oferta de Marketplace para consumidores externos.

Para obtener instrucciones sobre cómo publicar en un catálogo de servicios, consulte la serie de artículos sobre cómo [publicar en un catálogo de servicios](https://docs.microsoft.com/azure/managed-applications/publish-service-catalog-app).

### <a name="deploy-applications-from-the-service-catalog"></a>Implementación de aplicaciones desde el catálogo de servicios

1. En el Azure Portal, busque **Centro de Managed Applications (versión preliminar)** .
2. Haga clic en **Aplicaciones del catálogo de servicios** en la sección **Examinar** de la navegación del portal.
3. Haga clic en **+ Agregar** para seleccionar una definición de aplicación del catálogo de servicios de su empresa.

Las aplicaciones administradas a las que da mantenimiento se muestran aquí.

::: zone target="chromeless"

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/Microsoft_Azure_Appliance/ManagedAppsHubBlade/browseServiceCatalog]" submitText="Go to Virtual Machines" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

### <a name="manage-service-catalog-applications"></a>Administración de las aplicaciones del catálogo de servicios

1. En el Azure Portal, busque **Centro de Managed Applications (versión preliminar)** .
2. Haga clic en **Aplicaciones del catálogo de servicios** en la sección **Servicio** de la navegación del portal.

Las aplicaciones administradas a las que da mantenimiento se muestran aquí.

::: zone target="chromeless"

::: form action="OpenBlade[#blade/Microsoft_Azure_Appliance/ManagedAppsHubBlade/serviceServiceCatalogApps]" submitText="Go to Virtual Machines" :::

::: zone-end

::: zone target="docs"

## <a name="continuous-improvement"></a>Mejora continua

::: zone-end
::: zone target="chromeless"

## <a name="continuous-improvementtabcontinuousimprovement"></a>[Mejora continua](#tab/ContinuousImprovement)

::: zone-end

La especialización de la plataforma y las operaciones de la misma dependen de ciclos de comentarios sólidos entre los equipos de adopción, plataforma, automatización y administración. Si dichos ciclos de comentarios están basados en datos, cada equipo puede tomar decisiones acertadas. En el caso de las operaciones de plataforma para lograr compromisos empresariales a largo plazo, es importante aprovechar la información específica de la plataforma centralizada. Dado que los contenedores y SQL Server son las dos plataformas administradas centralmente más comunes, los siguientes son algunos artículos que le ayudarán a empezar a usar la recopilación de datos para mejora continua.

[Rendimiento de contenedores](https://docs.microsoft.com/azure/azure-monitor/insights/container-insights-overview)
[Rendimiento de base de datos PaaS](https://docs.microsoft.com/azure/azure-monitor/insights/azure-sql)
[Rendimiento de base de datos IaaS](https://docs.microsoft.com/azure/azure-monitor/insights/sql-assessment)
