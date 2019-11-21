---
title: 'Guía sobre la supervisión en la nube: recopilación de los datos correctos'
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: Decida cuándo usar Azure Monitor o System Center Operations Manager en Microsoft Azure.
author: MGoedtel
ms.author: magoedte
ms.date: 06/26/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: operate
services: azure-monitor
ms.openlocfilehash: 950b767101fea9b33875f1ad0938599a4f371ba9
ms.sourcegitcommit: 6f287276650e731163047f543d23581d8fb6e204
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73751517"
---
# <a name="cloud-monitoring-guide-collect-the-right-data"></a>Guía sobre la supervisión en la nube: recopilación de los datos correctos

En este artículo se describen algunas consideraciones para recopilar datos de supervisión en una aplicación de la nube.

Para observar el estado y la disponibilidad de la solución en la nube, debe configurar las herramientas de supervisión para recopilar un nivel de señales que se basen en estados de error predecibles. Estas señales son los síntomas del error, no la causa. Las herramientas de supervisión usan métricas y, para los diagnósticos avanzados y los análisis de la causa principal, usan registros.

Planee cuidadosamente la supervisión y la migración. Para empezar, incluya al propietario del servicio de supervisión, al administrador de las operaciones y a otro personal relacionado durante la fase de planeamiento y continúe contando con ellos en todo el ciclo de desarrollo y lanzamiento. Su enfoque será desarrollar una configuración de supervisión basada en los criterios siguientes:

- ¿Cuál es la composición del servicio y son esas las dependencias supervisadas hoy? Si es así, ¿hay varias herramientas implicadas? ¿Hay alguna oportunidad de consolidarla, sin introducir riesgos?
- ¿Cuál es el Acuerdo de Nivel de Servicio y cómo se mide y se notifica?
- ¿Qué aspecto debería tener el panel de servicio cuando se produce un incidente? ¿Qué aspecto debería tener el panel para el propietario del servicio y el equipo que respalda el servicio?
- ¿Qué métricas genera el recurso que se debe supervisar?  
- ¿Cómo realizarán búsquedas los registros el propietario del servicio, los equipos de soporte técnico y otro personal?

El modo en que se responda a esas preguntas, y los criterios de alerta, determinarán cómo se usará la plataforma de supervisión. Si va a migrar desde una plataforma de supervisión o un conjunto de herramientas de supervisión existentes, use la migración como una oportunidad para volver a evaluar las señales que recopile. Esto es especialmente cierto ahora que hay varios factores de costo que se deben tener en cuenta durante la migración o integración con una plataforma de supervisión basada en la nube como Azure Monitor. Recuerde que los datos de supervisión deben ser procesables. Es necesario haber recopilado datos optimizados para tener una buena visión general del estado del servicio. La instrumentación que está definida para identificar incidentes reales debe ser tan sencilla, predecible y confiable como sea posible.

## <a name="develop-a-monitoring-configuration"></a>Desarrollo de una configuración de supervisión

El equipo y el propietario del servicio de supervisión normalmente siguen un conjunto común de actividades para desarrollar una configuración de supervisión. Estas actividades se inician en las fases de planeación iniciales, continúan con las pruebas y se validan en un entorno que no es de producción; posteriormente, se amplían para implementarse en producción. Las configuraciones de supervisión se derivan de modos de error conocidos, de resultados de pruebas de errores simulados y de la experiencia de varias personas de la organización (el departamento de servicios, las operaciones, los ingenieros y los desarrolladores). En tales configuraciones se supone que el servicio ya existe, se está migrando a la nube y no se ha rediseñado.

Para obtener los resultados de calidad del nivel de servicio, supervise el estado y la disponibilidad de estos servicios al principio del proceso de desarrollo. Si supervisa el diseño del servicio o aplicación como una ocurrencia tardía, los resultados no serán tan buenos.

Para impulsar una resolución más rápida del incidente, tenga en cuenta las siguientes recomendaciones:

- Defina un panel para cada componente de servicio.
- Use métricas que ayuden a guiar un diagnóstico posterior y a identificar una solución definitiva o temporal del problema en caso de que no se pueda descubrir la causa principal.
- Use las funcionalidades de exploración en profundidad del panel o respalde la personalización de la vista para mejorarla.
- Si necesita registros detallados, las métricas deberían haber ayudado a identificar los criterios de búsqueda. Si las métricas no resultaron de ayuda, se pueden mejorar para el siguiente incidente.

La adopción de este conjunto de principios puede ayudarle a obtener información casi en tiempo real, así como una mejor administración del servicio.

## <a name="next-steps"></a>Pasos siguientes

> [!div class="nextstepaction"]
> [Estrategia de alertas](./alerting.md)
