---
title: 'Cumplimiento operativo: administración de la nube y operaciones'
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: 'Cumplimiento operativo: administración de la nube y operaciones'
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.openlocfilehash: bb6e4584da87d992f85b6ce90e21081c9c19d7c3
ms.sourcegitcommit: f3371811a36e12533ecbc3aa936e2a68e0cee25f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2019
ms.locfileid: "72682542"
---
# <a name="operational-compliance-in-cloud-management"></a>Cumplimiento operativo en la administración de la nube

El cumplimiento operativo se basa en la materia de [inventario y visibilidad](./inventory.md) como primer paso factible en la administración de la nube. Esta materia se centra en las revisiones habituales de los datos de telemetría y en los trabajos de corrección (tanto activos como reactivos). Esta materia es la piedra angular para mantener el equilibrio entre la seguridad, la gobernanza, el rendimiento y los costos.

## <a name="components-of-operations-compliance"></a>Componentes del cumplimiento operativo

Mantener el cumplimiento de los compromisos operativos requiere análisis, automatización y corrección humana. Para un cumplimiento operativo eficaz se requiere coherencia en algunos procesos críticos:

1. Coherencia de recursos
2. Coherencia del entorno
3. Coherencia en la configuración de los recursos
4. Coherencia de actualización
5. Automatización de las correcciones

### <a name="resource-consistency"></a>Coherencia de recursos

El paso más eficaz que puede dar un equipo de administración de la nube para el cumplimiento operativo es establecer la coherencia en la organización de los recursos y el etiquetado. La coherencia de organización y etiquetado de los recursos facilita las demás tareas operativas. Para instrucciones más detalladas sobre la coherencia de los recursos, consulte la [fase de gobernanza](../../govern/index.md) durante la adopción en la nube. En concreto, los [artículos sobre la base de gobernanza inicial](../../govern/initial-foundation.md) muestran ejemplos de maneras de empezar a desarrollar la coherencia de los recursos.

### <a name="environment-consistency"></a>Coherencia del entorno

Los entornos coherentes, o zonas de aterrizaje, son el siguiente paso más importante hacia el cumplimiento operativo. Con zonas de aterrizaje coherentes y que se aplican mediante herramientas automatizadas, el diagnóstico y la resolución de problemas operativos son considerablemente menos complejos. Para instrucciones más detalladas sobre la coherencia del entorno, consulte la [fase de preparación](../../ready/index.md) durante la adopción en la nube. En esta fase, los ejercicios establecen un proceso repetible para definir y madurar un enfoque coherente basado primero en código para el desarrollo de entornos basados en la nube.

### <a name="resource-configuration-consistency"></a>Coherencia en la configuración de los recursos

En función de los enfoques de gobernanza y preparación, la administración de la nube debe incluir procesos para la supervisión y la evaluación continuas del cumplimiento de los requisitos de coherencia de los recursos. A medida que las cargas de trabajo cambian o se adoptan nuevas versiones, es fundamental que los procesos de administración de la nube evalúen los cambios de configuración, que no se regulan fácilmente con medios automatizados.

Cuando se detectan irregularidades, algunas se solucionan por coherencia en las actualizaciones y otras se pueden corregir automáticamente.

### <a name="update-consistency"></a>Coherencia de actualización

La estabilidad puede conducir a operaciones estables. Sin embargo, se necesitan algunos cambios en los procesos de administración de la nube. En concreto, es esencial realizar cambios en el rendimiento y revisiones habituales para reducir las interrupciones y controlar los costos.

Una de las muchas ventajas de una metodología de administración de la nube madura es la estabilización y el control de los cambios necesarios.

Cualquier base de referencia de administración de la nube debe incluir un medio para programar, controlar y, posiblemente, automatizar las actualizaciones necesarias. Estas actualizaciones deben incluir como mínimo revisiones, pero también pueden incluir rendimiento, ajuste de tamaño y otros aspectos de la actualización de los recursos.

### <a name="remediation-automation"></a>Automatización de las correcciones

Como base de referencia mejorada para la administración de la nube, algunas cargas de trabajo pueden beneficiarse de la corrección automatizada. Cuando con frecuencia una carga de trabajo detecta problemas que no se pueden resolver mediante cambios de código o de arquitectura, la automatización de correcciones puede reducir la carga de la administración de la nube para mayor satisfacción del usuario.

Muchos dirían que cualquier problema lo suficientemente común para automatizarse, debería solucionarse mediante la resolución de la deuda técnica. Cuando sea prudente la resolución a largo plazo, debe ser la opción predeterminada. Sin embargo, hay una serie de escenarios empresariales que dificultan la justificación de grandes inversiones en la resolución de la deuda técnica. Cuando no se puede justificar la resolución de la deuda técnica, pero la corrección es una carga común y costosa, la corrección automatizada es la siguiente mejor solución.

## <a name="next-steps"></a>Pasos siguientes

[Protección y recuperación](./protect.md), esas son las siguientes áreas que se deben considerarse en una base de referencia para la administración de la nube.

> [!div class="nextstepaction"]
> [Protección y recuperación](./protect.md)
