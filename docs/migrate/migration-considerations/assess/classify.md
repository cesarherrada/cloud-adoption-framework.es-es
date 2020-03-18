---
title: Clasificación de la carga de trabajo antes de la migración
description: Clasifique las cargas de trabajo durante una evaluación previa a la migración.
author: BrianBlanchard
ms.author: brblanch
ms.date: 03/03/2020
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: migrate
ms.openlocfilehash: 8f912891bf90d0ecef29727d7d7a067d442234fc
ms.sourcegitcommit: 959cb0f63e4fe2d01fec2b820b8237e98599d14f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2020
ms.locfileid: "79095392"
---
# <a name="workload-classification-before-migration"></a>Clasificación de la carga de trabajo antes de la migración

Durante cada iteración de un proceso de migración, una o más cargas de trabajo se migrarán y promoverán a producción. Antes de realizar estas actividades de migración, es importante clasificar cada carga de trabajo. La clasificación ayuda a aclarar los requisitos de gobernanza, seguridad, operaciones y administración de datos.

La siguiente guía se basa en los requisitos de etiquetado sugeridos que se describen en el [artículo sobre los estándares de nomenclatura y etiquetado](../../../ready/azure-best-practices/naming-and-tagging.md#metadata-tags), y agrega importantes [operaciones](../../../manage/considerations/criticality.md#criticality-scale) y elementos de [gobernanza](../../../govern/guides/complex/prescriptive-guidance.md#resource-tagging).

En este artículo, se recomienda específicamente agregar el grado de importancia y la confidencialidad de los datos a los estándares de etiquetado existentes. Cada uno de estos puntos de datos ayudará a otros equipos a comprender qué cargas de trabajo pueden requerir atención o soporte técnico adicional.

## <a name="data-sensitivity"></a>Confidencialidad de los datos

Como se describe en el artículo sobre [clasificación de datos](../../../govern/policy-compliance/data-classification.md), esta mide el impacto que tendría una fuga de datos en la empresa o los clientes. Los equipos de gobernanza y seguridad utilizan la confidencialidad o la clasificación de los datos como un indicador de riesgo para la seguridad. Durante la evaluación, el equipo de adopción de la nube debe evaluar la clasificación de los datos para cada carga de trabajo destinada a la migración y compartir esa clasificación con los equipos auxiliares. Es posible que las cargas de trabajo que tratan estrictamente con "datos públicos" no afecten a los equipos auxiliares. Sin embargo, a medida que los datos se mueven hacia el extremo "extremadamente confidencial" del espectro, es probable que tanto los equipos de gobernanza como los de seguridad tengan interés en participar en la evaluación de la carga de trabajo.

Trabaje con los equipos de seguridad y gobernanza tan pronto como sea posible para definir los siguientes elementos:

- Un proceso claro para compartir las cargas del trabajo pendiente que incluyan datos confidenciales.
- La comprensión de los requisitos de gobernanza y de base de referencia de seguridad necesarios para los distintos niveles de confidencialidad de los datos.
- Cualquier impacto que la confidencialidad de los datos pueda tener en el diseño de las suscripciones, las jerarquías de los grupos de administración o los requisitos de la zona de aterrizaje.
- Cualquier requisito para probar la clasificación de datos, que puede incluir herramientas específicas o un ámbito de clasificación definido.

## <a name="mission-criticality"></a>Grado de importancia de la misión

Tal y como se describe en el artículo sobre el [grado de importancia de la carga de trabajo](../../../manage/considerations/criticality.md), este valor indica en qué medida se verá afectado el negocio durante una interrupción. Este punto de datos ayuda a los equipos de seguridad y administración de operaciones a evaluar los riesgos relacionados con las interrupciones y las vulneraciones. Durante la evaluación, el equipo de adopción de la nube debe evaluar el grado de importancia de la misión de cada carga de trabajo destinada a la migración y compartir esa clasificación con los equipos auxiliares. Es probable que las cargas de trabajo con un grado "bajo" o "no compatibles" tengan poco impacto en los equipos auxiliares. Sin embargo, a medida que las cargas de trabajo se aproximan a las clasificaciones de grado "crítico para la misión" o "crítico para la unidad", sus dependencias operativas se hacen más evidentes.

Trabaje con los equipos de operaciones y seguridad tan pronto como sea posible para definir los siguientes elementos:

- Un proceso claro para compartir las cargas del trabajo pendiente con requisitos de soporte técnico.
- La comprensión de los requisitos de administración de operaciones y coherencia de recursos para los diferentes grados de importancia.
- Cualquier impacto que el grado de importancia pueda tener en el diseño de las suscripciones, las jerarquías de los grupos de administración o los requisitos de la zona de aterrizaje.
- Cualquier requisito necesario para documentar el grado de importancia, que puede incluir informes de uso o tráfico específicos, análisis financieros u otras herramientas.

## <a name="next-steps"></a>Pasos siguientes

Una vez que las cargas de trabajo están clasificadas correctamente, es mucho más fácil [alinear las prioridades empresariales](./business-priorities.md).

> [!div class="nextstepaction"]
> [Alineación de las prioridades empresariales](./business-priorities.md)
