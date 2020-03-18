---
title: Evaluación de cada carga de trabajo y perfeccionamiento de planes
description: Use Cloud Adoption Framework para Azure con el fin de evaluar la idoneidad de su entorno para la migración y qué métodos debe tener en cuenta.
author: matticusau
ms.author: mlavery
ms.date: 02/25/2020
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: migrate
ms.custom: fasttrack-new, AQC
ms.localizationpriority: high
ms.openlocfilehash: 47cfc7bdbf823ad8a785705e361ba8fa1a44894f
ms.sourcegitcommit: 959cb0f63e4fe2d01fec2b820b8237e98599d14f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2020
ms.locfileid: "79094335"
---
# <a name="assess-each-workload-and-refine-plans"></a>Evaluación de cada carga de trabajo y perfeccionamiento de planes

Los recursos de esta guía le ayudarán a evaluar cada carga de trabajo, a cuestionar las suposiciones sobre la idoneidad de cada una de ellas para la migración y a tomar decisiones arquitectónicas sobre las opciones de migración.

<!-- markdownlint-disable MD025 -->

# <a name="tools"></a>[Herramientas](#tab/Tools)

Si no ha seguido las instrucciones de los vínculos anteriores, es probable que necesite datos y una herramienta de evaluación para tomar decisiones bien fundamentadas sobre la migración. Azure Migrate es la herramienta nativa para realizar la evaluación **y** migración a Azure. Si todavía no lo ha hecho, siga estos pasos para crear un nuevo proyecto de migración de servidores y recopile los datos necesarios.

## <a name="azure-migrate"></a>Azure Migrate

Azure Migrate evalúa la infraestructura, las aplicaciones y los datos locales para su migración a Azure. Este servicio:

- Evalúa la idoneidad para la migración de los recursos locales.
- Realiza el ajuste de tamaño según el rendimiento.
- Proporciona estimaciones de costos para la ejecución de recursos locales en Azure.

Si está considerando utilizar un enfoque lift-and-shift o se encuentra en las primeras fases de la evaluación de la migración, este es el servicio que debe elegir. Después de completar la evaluación, use Azure Migrate para ejecutar la migración.

![Información general de Azure Migrate](./media/assess/azure-migrate-overview-1.png)

### <a name="create-a-new-server-migration-project"></a>Creación de un nuevo proyecto de migración de servidor

Inicie una evaluación de migración del servidor con Azure Migrate mediante estos pasos:

1. Seleccione **Azure Migrate**.
1. En **Información general**, seleccione **Evaluar y migrar servidores**.
1. Seleccione **Agregar herramientas**.
1. En **Detectar, evaluar y migrar servidores**, seleccione **Agregar herramientas**.
1. En **Proyecto de migración**, seleccione la suscripción a Azure y cree un grupo de recursos, en caso de que no lo tenga.
1. En **Detalles del proyecto**, especifique el nombre del proyecto y la zona geográfica en la que quiere crearlo; después, seleccione **Siguiente**.
1. En **Seleccione una herramienta de evaluación**, seleccione **Omitir por ahora la adición de una herramienta de evaluación > Siguiente**.
1. En **Seleccione una herramienta de migración**, seleccione **Azure Migrate: Migración del servidor > Siguiente**.
1. En **Revisar y agregar herramientas**, revise la configuración y seleccione **Agregar herramientas**.
1. Después de agregar la herramienta, aparece en el **proyecto de Azure Migrate > Servidores > Herramientas de migración**.

::: zone target="chromeless"

::: form action="OpenBlade[#blade/Microsoft_Azure_Migrate/AmhResourceMenuBlade/overview]" submitText="Assess and migrate servers" :::

::: zone-end

::: zone target="docs"

### <a name="learn-more"></a>Más información

- [Información general de Azure Migrate](https://docs.microsoft.com/azure/migrate/migrate-services-overview).
- [Migración de servidores físicos o virtualizados a Azure](https://docs.microsoft.com/azure/migrate/tutorial-migrate-physical-virtual-machines)
- [Azure Migrate en Azure Portal](https://portal.azure.com/#blade/Microsoft_Azure_Migrate/AmhResourceMenuBlade/overview).

::: zone-end

## <a name="service-map"></a>Mapa de servicio

Mapa de servicio detecta automáticamente los componentes de la aplicación en sistemas Windows y Linux y asigna la comunicación entre servicios. Con Service Map puede ver los servidores en la forma en que piensa en ellos: como sistemas interconectados que ofrecen servicios críticos. Service Map muestra las conexiones entre servidores, procesos, la latencia de conexión entrante y saliente y puertos en cualquier arquitectura conectada de TCP sin necesidad de ninguna configuración más allá de la instalación de un agente.

Azure Migrate utiliza Service Map para mejorar las funcionalidades de generación de informes y las dependencias en todo el entorno. Para conocer los detalles completos de esta integración, consulte [Visualización de dependencias](https://docs.microsoft.com/azure/migrate/concepts-dependency-visualization). Si usa el servicio de migración de Azure, no se requieren pasos adicionales para configurar y obtener las ventajas de Service Map. Las instrucciones siguientes se proporcionan para su consulta si quiere usar Service Map para otros propósitos o proyectos.

### <a name="enable-dependency-visualization-using-service-map"></a>Habilitación de la visualización de dependencias con Service Map

Para usar la visualización de dependencias, descargue e instale agentes en cada máquina local que vaya a analizar.

- Se debe instalar [Microsoft Monitoring Agent (MMA)](https://docs.microsoft.com/azure/log-analytics/log-analytics-agent-windows) en cada máquina.
- Se debe instalar [Microsoft Dependency Agent](https://docs.microsoft.com/azure/azure-monitor/insights/vminsights-enable-hybrid-cloud#install-the-dependency-agent-on-windows) en cada máquina.
- Si también tiene máquinas sin conectividad a Internet, descargue e instale en ellas la puerta de enlace de Log Analytics.

<!-- markdownlint-disable MD024 -->

### <a name="learn-more"></a>Más información

- [Uso de la solución Service Map en Azure](https://docs.microsoft.com/azure/azure-monitor/insights/service-map)
- [Azure Migrate y Service Map: Visualización de dependencias](https://docs.microsoft.com/azure/migrate/concepts-dependency-visualization)

# <a name="challenge-assumptions"></a>[Cuestionamiento de suposiciones](#tab/Challenge-Assumptions)

En una migración ideal, cada recurso (infraestructura, aplicación o datos) sería compatible con una plataforma en la nube y estaría listo para su migración o modernización. En la realidad, no todas las cargas de trabajo se deben migrar a la nube. No todos los recursos son compatibles con las plataformas en la nube. Antes de migrar una carga de trabajo a la nube, evalúe cada carga de trabajo y todos los recursos dependientes (infraestructura, aplicaciones y datos).

El [plan metodológico para Cloud Adoption Framework](../../plan/index.md) recomienda a los lectores utilizar la [racionalización incremental](../../digital-estate/rationalize.md#incremental-rationalization) y los enfoques de [potencias de diez](../../digital-estate/rationalize.md#release-planning) para evaluar y planear la migración. Esa guía también incluye un procedimiento recomendado detallado sobre el [uso de Azure Migrate para evaluar su patrimonio digital](../../plan/contoso-migration-assessment.md).

Los vínculos anteriores sugieren que se aceptan suposiciones y que, a menudo, estas son recomendables durante las fases de planeamiento de la migración. Pero, ahora, es momento de pasar a la acción. Se deben cuestionar esas suposiciones en cada carga de trabajo antes de migrar a la nube.

## <a name="two-steps-of-incremental-rationalization"></a>Dos pasos de racionalización incremental

Se requieren dos pasos igual de importantes para proporcionar satisfactoriamente la [racionalización incremental](../../digital-estate/rationalize.md#incremental-rationalization). Ambos pasos requieren datos y conclusiones sobre el entorno. No obstante, cada enfoque respeta la cantidad de tiempo y el nivel de detalle necesarios para la realización de correcta de un esfuerzo de migración.

- **[Planeamiento de versiones del enfoque de la potencia de 10](../../digital-estate/rationalize.md#release-planning):** Durante la racionalización inicial y el planeamiento de versiones, solo se usará una de las [5 "R" de la racionalización](../../digital-estate/5-rs-of-rationalization.md) en la evaluación. Realice estimaciones y planes en función de la opción de racionalización que se mejor se adapte a las motivaciones generales definidas en el [documento de estrategias de adopción de la nube](https://archcenter.blob.core.windows.net/cdn/fusion/readiness/Microsoft-Cloud-Adoption-Framework-Strategy-and-Plan-Template.docx).

- **Evaluación detallada de cada carga de trabajo:** Las suposiciones asociadas al planeamiento de versiones de potencias de 10 son lo suficientemente aceptables para crear un plan. Pero esas mismas suposiciones pueden provocar problemas significativos si no se evalúan antes de la migración.

## <a name="challenge-assumptions-and-update-the-plan"></a>Cuestionamiento de las suposiciones y actualización del plan

Revise concienzudamente los datos de evaluación en Azure Migrate o en la herramienta de evaluación elegida. Estos datos proporcionarán información sobre problemas de compatibilidad, requisitos de corrección, sugerencias de ajuste de tamaño y otros aspectos.

Antes de la migración, use esos datos, junto con las conversaciones de detección con el propietario del producto, los equipos de desarrollo, los administradores, etc., para evaluar la viabilidad de la migración de esta carga de trabajo concreta. Use esta detección para cuestionar las suposiciones principales acerca de esta carga de trabajo. Si los hallazgos cambian la migración o el plan de adopción, actualice el plan como corresponda.

El primer paso a la hora de cuestionar estas suposiciones es una [revisión de las 5 "R"](../../digital-estate/rationalize.md).

    - ¿Funciona el enfoque de racionalización supuesto para esta carga de trabajo? ¿Es el mejor enfoque?
    - ¿Afectará la [física de la replicación](../migration-considerations/migrate/replicate.md#replication-risks---physics-of-replication) a la migración de esta carga de trabajo?
    - ¿Requiere esta carga de trabajo alguna [actividad de corrección](../migration-considerations/assess/evaluate.md) antes de la migración?

Este tipo de preguntas ayuda a cuestionar las suposiciones y conduce al mejor enfoque para cada carga de trabajo.

Para obtener una lista más amplia de preguntas y un proceso definido para validar suposiciones, consulte la [introducción a la mejora de procesos de evaluación](../migration-considerations/assess/index.md).

# <a name="scenarios-and-stakeholders"></a>[Escenarios y partes interesadas](#tab/Scenarios)

## <a name="scenarios"></a>Escenarios

En esta guía se tratan los escenarios siguientes:

- **Hardware heredado:** lleva a cabo la migración para quitar una dependencia del hardware heredado que está llegando al final del soporte técnico o al final de su ciclo de vida.
- **Aumento de la capacidad:** aumente la capacidad de los recursos (infraestructura, aplicaciones y datos) que la infraestructura actual no puede proporcionar.
- **Modernización del centro de datos:** amplíe su centro de datos o modernícelo con la tecnología de nube para asegurarse de que su empresa sigue siendo actual y competitiva.
- **Modernización de aplicaciones o servicios:** actualice las aplicaciones para aprovechar las ventajas de la funcionalidad nativa de la nube. Incluso si la migración de rehospedaje es su objetivo inicial, la capacidad de crear planes para la revisión de aplicaciones o servicios y una posible modernización es un proceso común en cualquier migración.

### <a name="organizational-alignment-and-stakeholders"></a>Alineación de la organización y partes interesadas

La lista completa de las partes interesadas varía entre los proyectos de migración. Es mejor suponer que no conocerá a todas las partes interesadas al principio del planeamiento de una migración, ya que estas a menudo solo se identifican durante determinadas fases del proyecto. Sin embargo, antes de iniciar cualquier proyecto de migración, identifique a los principales directivos de finanzas, infraestructura de TI y grupos de aplicaciones que tienen interés en los esfuerzos generales de migración a la nube de su organización.

Establecer un equipo de estrategia de la nube principal, basado en estas partes interesadas clave de alto nivel, puede ayudar a preparar su organización para la adopción de la nube y guiar los esfuerzos generales de migración a la nube. Este equipo es responsable de comprender las tecnologías de nube y los procesos de migración, identificar la justificación comercial de las migraciones y determinar las mejores soluciones de alto nivel para los esfuerzos de migración. También ayuda a identificar y trabajar con partes interesadas del ámbito empresarial y aplicaciones específicas para garantizar una migración correcta.

Para más información sobre cómo preparar su organización para los esfuerzos de migración a la nube, consulte la guía de Cloud Adoption Framework sobre la [alineación inicial de la organización](../../plan/initial-org-alignment.md).

# <a name="timelines"></a>[Escalas de tiempo](#tab/Timelines)

Los clientes consideran normalmente que el escenario de migración que se trata en esta guía se puede completar en un plazo que va de uno a seis meses.

A la hora de evaluar la escala de tiempo de la migración, tenga en cuenta:

- **Los recursos (infraestructura, aplicaciones y datos)que se van a migrar:** la cantidad y diversidad de los recursos.
- **La preparación del personal:** ¿el personal está preparado para administrar el nuevo entorno o se necesita entrenamiento?
- **La financiación:** ¿tiene la aprobación y el presupuesto adecuados para completar la migración?
- **La administración de cambios:** ¿su empresa tiene requisitos específicos relacionados con la implementación y la aprobación de los cambios?
- **Las normativas relacionadas con el segmento:** ¿tiene que cumplir con la normativa del segmento o del sector?

# <a name="cost-management"></a>[Administración de costos](#tab/ManageCost)

La evaluación del entorno proporciona una gran oportunidad para incluir un paso de análisis de costos. Con los datos recopilados por las actividades de evaluación, debería poder analizar y predecir los costos. Esta predicción de costos debe factorizar los costos de servicios de consumo, además de los costos de un solo uso (como una mayor entrada de datos).

Durante la migración, hay algunos factores que afectan a las actividades de decisiones y ejecución:

- **El tamaño del patrimonio digital:** comprender el tamaño del patrimonio digital afectará directamente a las decisiones y los recursos necesarios para realizar la migración.
- **Modelos de contabilidad:** cambiar de un modelo de gastos de capital estructurados a un modelo de gastos operativos fluidos.

::: zone target="docs"

En los recursos siguientes se proporciona información relacionada:

- [Estimación del costo de la nube](../migration-considerations/assess/estimate.md)

::: zone-end
