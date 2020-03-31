---
title: Optimización de las cargas de trabajo migradas
description: Use Cloud Adoption Framework para Azure para preparar la carga de trabajo y los recursos migrados para promoverlos a producción.
author: BrianBlanchard
ms.author: brblanch
ms.date: 04/04/2019
ms.topic: conceptual
ms.service: cloud-adoption-framework
ms.subservice: migrate
ms.openlocfilehash: 9f078f3fb989c6db9ca14371c2fadd17805d4d3a
ms.sourcegitcommit: afe10f97fc0e0402a881fdfa55dadebd3aca75ab
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2020
ms.locfileid: "80432274"
---
# <a name="optimize-migrated-workloads"></a>Optimización de las cargas de trabajo migradas

Una vez que se ha migrado a la nube una carga de trabajo y sus recursos de apoyo, se debe preparar esa carga de trabajo para pasar a producción. En este proceso, las actividades preparan la carga de trabajo, ajustan el tamaño de los recursos dependientes y preparan el negocio para cuando la carga de trabajo migrada basada en la nube empiece a usarse en producción.

El objetivo de la optimización consiste en preparar una carga de trabajo migrada para su utilización en producción.

## <a name="definition-of-done"></a>Definición de *Listo*

El proceso de optimización estará completo cuando una carga de trabajo se haya configurado correctamente, se haya ajustado su tamaño y se haya implementado en producción.

## <a name="accountability-during-optimization"></a>Responsabilidad durante la optimización

El equipo de adopción de la nube es responsable de todo el proceso de optimización. No obstante, los miembros del equipo de estrategia en la nube, el equipo de operaciones en la nube y el equipo de gobernanza de la nube también deben ser responsables de las actividades de este proceso.

## <a name="responsibilities-during-optimization"></a>Responsabilidades durante la optimización

Además de la responsabilidad de alto nivel, hay acciones de las que un individuo o grupo se deben hacer responsables directamente. Estas son algunas de las actividades que se tienen que asignar a las partes responsables:

- **Pruebas empresariales.** Resuelva los problemas de compatibilidad que impidan que la carga de trabajo complete su migración a la nube.
  - Los usuarios avanzados de la empresa deben participar activamente en las pruebas de la carga de trabajo migrada. Según el grado de optimización que haya intentado, puede que necesite varios ciclos de pruebas.
- **Plan de cambio de negocio.** El desarrollo de un plan para la adopción del usuario, los cambios en los procesos empresariales y la modificación de los KPI empresariales o las métricas de aprendizaje son el resultado del esfuerzo de migración.
- **Realización de pruebas comparativas y optimización.** Análisis de las pruebas empresariales y de las pruebas automatizadas para comparar el rendimiento. Según el uso, el equipo de adopción de la nube ajusta el tamaño de los recursos implementados para equilibrar el costo y el rendimiento según los requisitos de producción esperados.
- **Listo para producción.** Prepare la carga de trabajo y el entorno para que sea compatible con la utilización continua en producción de la carga de trabajo.
- **Promoción.** Redirija el tráfico de producción a la carga de trabajo migrada y optimizada. Esta actividad representa la finalización de un ciclo de migración.

Además de las actividades básicas, hay algunas actividades paralelas que requieren asignaciones específicas y planes de ejecución:

- **Dar de baja.** Por lo general, se pueden obtener ahorros en el costo de una migración, si se dan de baja los recursos de producción anteriores y se eliminan adecuadamente.
- **Retrospectiva.** Cada ciclo de migración crea una oportunidad de aprendizaje más profundo y la adopción de una mentalidad de crecimiento. Cuando se completa cada ciclo de migración, el equipo de adopción de la nube debe evaluar los procesos usados durante la migración para identificar las mejoras.

## <a name="next-steps"></a>Pasos siguientes

Con un conocimiento general del proceso de optimización, estará listo para comenzar el proceso mediante el [establecimiento de un plan de cambio empresarial para la carga de trabajo candidata a la migración](./business-change-plan.md).

> [!div class="nextstepaction"]
> [Plan de cambio empresarial](./business-change-plan.md)
