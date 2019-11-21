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
ms.openlocfilehash: 8c3954627ee991f43c2b8d3a94dbd77746d3d4b2
ms.sourcegitcommit: 6f287276650e731163047f543d23581d8fb6e204
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73752940"
---
# <a name="platform-specialization-for-cloud-management"></a>Especialización de la plataforma para la administración en la nube

Al igual que la línea de base de administración mejorada, la especialización de plataforma es una extensión más allá de la línea de base de administración estándar. Consulte la lista y la imagen siguientes, que muestran las maneras de ampliar la línea de referencia de administración. En este artículo se tratan las opciones de especialización de la plataforma.

![Más allá de la línea base de administración en la nube](../../_images/manage/beyond-the-baseline.png)

- **Operaciones con cargas de trabajo:** mayor inversión en operaciones por carga de trabajo y mayor grado de resistencia. Las operaciones con cargas de trabajo se sugieren para aproximadamente el 20 % de las cargas de trabajo que impulsan el valor empresarial. Esta especialización suele reservarse para cargas de trabajo de gran importancia o críticas.
- **Operaciones de la plataforma:** La inversión en operaciones se reparte entre varias cargas de trabajo. Las mejoras de resistencia afectan a todas las cargas de trabajo que usan la plataforma definida. Las operaciones de la plataforma se sugieren para aproximadamente el 20 % de las plataformas que tienen una importancia crítica. Esta especialización se suele reservar para cargas de trabajo de importancia media a crítica.
- **Línea de base de administración mejorada:** inversión en operaciones relativamente más baja. Esta especialización mejora ligeramente los compromisos empresariales mediante herramientas y procesos de operaciones nativos de la nube.

Ambas operaciones de carga de trabajo y plataforma requieren cambios en los principios de diseño y arquitectura. Estos cambios pueden tardar un tiempo y generar mayores gastos de funcionamiento. Para reducir el número de cargas de trabajo que requieren tales inversiones, una línea de referencia de administración mejorada puede proporcionar una mejora suficiente en el compromiso empresarial.

En esta tabla se describen algunos procesos, herramientas y posibles consecuencias comunes en las líneas de referencia de administración mejorada de los clientes:

|Proceso  |Herramienta  |Propósito  |Nivel de administración sugerido  |
|---------|---------|---------|---------|
|Mejora del diseño del sistema|Marco de arquitectura de Azure|Mejora del diseño arquitectónico de la plataforma para mejorar las operaciones|N/D|
|Corrección automática|Azure Automation|Respuesta a datos avanzados de la plataforma con automatización específica de la plataforma|Operaciones de la plataforma|
|Catálogo de servicios|Centro de Managed Applications|Suministro de un catálogo de autoservicio de soluciones aprobadas que cumplen los estándares de la organización|Operaciones de la plataforma|
|Rendimiento de contenedores|Azure Monitor para contenedores|Supervisión y diagnóstico de contenedores|Operaciones de la plataforma|
|Rendimiento de datos de la plataforma como servicio (PaaS)|Azure SQL Analytics|Supervisión y diagnóstico de bases de datos PaaS|Operaciones de la plataforma|
|Rendimiento de los datos de infraestructura como servicio (IaaS)|Comprobación de estado de SQL Server|Supervisión y diagnóstico de bases de datos IaaS|Operaciones de la plataforma|

## <a name="high-level-process"></a>Proceso de alto nivel

La especialización de la plataforma consta de una ejecución disciplinada de los cuatro procesos siguientes con un enfoque iterativo. Cada proceso se explica con más detalle en secciones posteriores de este artículo.

- **Mejora del diseño del sistema:** mejora el diseño de sistemas o plataformas comunes para minimizar las interrupciones de forma eficaz.
- **Corrección automática:** algunas mejoras no son rentables. En tales casos, es posible que tenga más sentido automatizar la corrección y reducir el efecto de las interrupciones.
- **Escalado de la solución:** a medida que se mejoran el diseño de sistemas y la corrección automatizada, los cambios se pueden escalar en el entorno a través del catálogo de servicios.
- **Mejora continua:** se pueden usar distintas herramientas de supervisión para detectar mejoras incrementales. Estas mejoras se pueden tratar en el siguiente paso del diseño, la automatización y la escala del sistema.

::: zone target="docs"

## <a name="improve-system-design"></a>Mejora del diseño del sistema

::: zone-end
::: zone target="chromeless"

## <a name="improve-system-designtabsystemsdesign"></a>[Mejora del diseño del sistema](#tab/SystemsDesign)

::: zone-end

La mejora del diseño del sistema es el enfoque más eficaz para mejorar las operaciones de cualquier plataforma común. Gracias a las mejoras en el diseño del sistema, la estabilidad puede aumentar y las interrupciones del negocio pueden disminuir. El diseño de sistemas individuales está fuera del ámbito de la vista del entorno adoptada en todo el marco de adopción de la nube de Azure.

Como complemento de este marco, el marco de arquitectura de Azure proporciona procedimientos recomendados para mejorar la resistencia y el diseño de un sistema específico. Estas mejoras de diseño se pueden aplicar al diseño de sistemas de una plataforma o una carga de trabajo específicas.

El marco de arquitectura de Azure se centra en la mejora de cinco pilares del diseño de sistemas:

- **Escalabilidad:** escalado de los recursos comunes de la plataforma para controlar el aumento de la carga.
- **Disponibilidad:** reducción de las interrupciones empresariales al mejorar el tiempo de actividad potencial.
- **Resistencia:** mejora de los tiempos de recuperación para reducir la duración de las interrupciones.
- **Seguridad:** protección de las aplicaciones y los datos frente a amenazas externas.
- **Administración:** procesos operativos específicos para los recursos comunes de la plataforma.

La deuda técnica y los errores arquitectónicos provocan la mayoría de las interrupciones de la empresa. En el caso de las implementaciones existentes, puede ver las mejoras en el diseño de los sistemas como pagos de la deuda técnica existente. En el caso de las nuevas implementaciones, puede ver estas mejoras como una medida para evitar la deuda técnica.

La pestaña **Corrección automatizada** siguiente examina las formas de abordar la deuda técnica que no se puede o no se debe solucionar.

Obtenga más información acerca del [marco de arquitectura de Azure](https://docs.microsoft.com/azure/architecture/guide/pillars) para mejorar el diseño del sistema.

A medida que el diseño del sistema mejora, vuelva a consultar este artículo para encontrar nuevas oportunidades de mejorar y escalar esas mejoras en todo el entorno.

::: zone target="docs"

## <a name="automated-remediation"></a>Corrección automatizada

::: zone-end
::: zone target="chromeless"

## <a name="automated-remediationtabautomatedremediation"></a>[Corrección automatizada](#tab/AutomatedRemediation)

::: zone-end

Algunas deudas técnicas no se pueden abordar, ya que la resolución puede tener un costo demasiado alto o haberse planeado, pero tener una duración de proyecto prolongada. Es posible que la interrupción empresarial no tenga un efecto importante para la empresa. O bien, la prioridad empresarial podría ser una recuperación rápida en lugar de la inversión en resistencia.

Cuando el enfoque deseado no es la resolución de la deuda técnica, la corrección automática suele ser el siguiente paso. El uso de Azure Automation y Azure Monitor para detectar tendencias y proporcionar una corrección automatizada es el enfoque más común para la corrección automatizada.

Para obtener instrucciones sobre la corrección automatizada, consulte [Azure Automation y alertas](https://docs.microsoft.com/azure/automation/automation-create-alert-triggered-runbook).

::: zone target="docs"

## <a name="scale-the-solution-with-a-service-catalog"></a>Escalado de la solución con un catálogo de servicios

::: zone-end
::: zone target="chromeless"

## <a name="scale-the-solution-with-a-service-catalogtabservicecatalog"></a>[Escalado de la solución con un catálogo de servicios](#tab/ServiceCatalog)

::: zone-end

La piedra angular de las operaciones la especialización de la plataforma es un catálogo de servicios bien administrado. A través del catálogo se escalan las mejoras en el diseño de los sistemas y las correcciones en un entorno.

El equipo de plataforma en la nube y el equipo de automatización en la nube se coordinan para crear soluciones repetibles para las plataformas más comunes en cualquier entorno. Sin embargo, si esas soluciones no se utilizan de forma coherente, la administración en la nube puede proporcionar poco más que una oferta de línea de referencia.

Para maximizar la adopción y minimizar la sobrecarga de mantenimiento de cualquier plataforma optimizada, dicha plataforma se debe agregar a un catálogo de servicios de Azure. Todas las aplicaciones del catálogo se pueden implementar para consumo interno a través del catálogo de servicios o como una oferta de Marketplace para consumidores externos.

Para obtener instrucciones sobre cómo publicar en un catálogo de servicios, consulte la serie de artículos sobre cómo [publicar en un catálogo de servicios](https://docs.microsoft.com/azure/managed-applications/publish-service-catalog-app).

### <a name="deploy-applications-from-the-service-catalog"></a>Implementación de aplicaciones desde el catálogo de servicios

1. En Azure Portal, busque **Centro de Managed Applications (versión preliminar)** .
2. En el panel **Examinar**, seleccione **Aplicaciones del catálogo de servicios**.
3. Haga clic en **+ Agregar** para seleccionar una definición de aplicación del catálogo de servicios de su empresa.

Se muestran las aplicaciones administradas a las que presta mantenimiento.

::: zone target="chromeless"

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/Microsoft_Azure_Appliance/ManagedAppsHubBlade/browseServiceCatalog]" submitText="Go to Virtual Machines" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

### <a name="manage-service-catalog-applications"></a>Administración de las aplicaciones del catálogo de servicios

1. En Azure Portal, busque **Centro de Managed Applications (versión preliminar)** .
1. En el panel **Servicio**, seleccione **Aplicaciones del catálogo de servicios**.

Se muestran las aplicaciones administradas a las que presta mantenimiento.

::: zone target="chromeless"

::: form action="OpenBlade[#blade/Microsoft_Azure_Appliance/ManagedAppsHubBlade/serviceServiceCatalogApps]" submitText="Go to Virtual Machines" :::

::: zone-end

::: zone target="docs"

## <a name="continuous-improvement"></a>Mejora continua

::: zone-end
::: zone target="chromeless"

## <a name="continuous-improvementtabcontinuousimprovement"></a>[Mejora continua](#tab/ContinuousImprovement)

::: zone-end

La especialización de la plataforma y las operaciones de la misma dependen de ciclos de comentarios sólidos entre los equipos de adopción, plataforma, automatización y administración. El hecho de que esos ciclos de comentarios estén basados en datos ayuda a cada equipo a tomar decisiones acertadas. En el caso de las operaciones de plataforma para lograr compromisos empresariales a largo plazo, es importante usar la información específica de la plataforma centralizada.

Containers y SQL Server son las dos plataformas administradas de forma centralizada más comunes. Estos artículos pueden ayudarle a empezar con la recopilación de datos de mejora continua en estas plataformas:

- [Rendimiento de contenedores](https://docs.microsoft.com/azure/azure-monitor/insights/container-insights-overview)
- [Rendimiento de bases de datos PaaS](https://docs.microsoft.com/azure/azure-monitor/insights/azure-sql)
- [Rendimiento de bases de datos IaaS](https://docs.microsoft.com/azure/azure-monitor/insights/sql-assessment)
