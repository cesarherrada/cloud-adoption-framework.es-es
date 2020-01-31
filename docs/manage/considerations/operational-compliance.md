---
title: 'Cumplimiento operativo: administración de la nube y operaciones'
description: 'Cumplimiento operativo: administración de la nube y operaciones'
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.openlocfilehash: f83ec1ced367cca89349188932e608604dc3a005
ms.sourcegitcommit: 2362fb3154a91aa421224ffdb2cc632d982b129b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76807757"
---
# <a name="operational-compliance-in-cloud-management"></a>Cumplimiento operativo en la administración de la nube

El cumplimiento operativo se basa en la materia de [inventario y visibilidad](./inventory.md). Como primer paso accionable de la administración de la nube, esta materia se centra en las revisiones habituales de los datos de telemetría y en los trabajos de corrección (tanto proactivos como reactivos). Esta materia es la piedra angular para mantener el equilibrio entre la seguridad, la gobernanza, el rendimiento y los costos.

## <a name="components-of-operations-compliance"></a>Componentes del cumplimiento operativo

Mantener el cumplimiento de los compromisos operativos requiere análisis, automatización y corrección humana. Para un cumplimiento operativo eficaz se requiere coherencia en algunos procesos críticos:

- Coherencia de recursos
- Coherencia del entorno
- Coherencia en la configuración de los recursos
- Coherencia de actualización
- Automatización de las correcciones

### <a name="resource-consistency"></a>Coherencia de recursos

El paso más eficaz que puede dar un equipo de administración de la nube para el cumplimiento operativo es establecer la coherencia en la organización de los recursos y el etiquetado. La coherencia de organización y etiquetado de los recursos facilita las demás tareas operativas. Para instrucciones más detalladas sobre la coherencia de los recursos, consulte la [fase de gobernanza](../../govern/index.md) durante la adopción en la nube. En concreto, los [artículos sobre la base de gobernanza inicial](../../govern/initial-foundation.md) muestran cómo empezar a desarrollar la coherencia de los recursos.

### <a name="environment-consistency"></a>Coherencia del entorno

Establecer entornos coherentes, o zonas de aterrizaje, son el siguiente paso más importante hacia el cumplimiento operativo. Con zonas de aterrizaje coherentes y que se aplican mediante herramientas automatizadas, el diagnóstico y la resolución de problemas operativos son considerablemente menos complejos. Para instrucciones más detalladas sobre la coherencia del entorno, consulte la [fase de preparación](../../ready/index.md) durante la adopción en la nube. En esta fase, los ejercicios ayudan a crear un proceso repetible para definir y madurar un enfoque coherente basado primero en código para el desarrollo de entornos basados en la nube.

### <a name="resource-configuration-consistency"></a>Coherencia en la configuración de los recursos

Dado que se basa en los enfoques de gobernanza y preparación, la administración de la nube debe incluir procesos para la supervisión y la evaluación continuas del cumplimiento de los requisitos de coherencia de los recursos. A medida que las cargas de trabajo cambian o se adoptan nuevas versiones, es fundamental que los procesos de administración de la nube evalúen los cambios de configuración, que no se regulan fácilmente a través de la automatización.

Cuando se detectan irregularidades, algunas se solucionan por coherencia en las actualizaciones y otras se pueden corregir automáticamente.

### <a name="update-consistency"></a>Coherencia de actualización

La estabilidad del enfoque puede dar lugar a operaciones más estables. Sin embargo, se necesitan algunos cambios en los procesos de administración de la nube. En concreto, es esencial realizar cambios en el rendimiento y revisiones habituales para reducir las interrupciones y controlar los costos.

Una de las muchas ventajas de una metodología de administración de la nube madura es centrarse en la estabilización y el control de los cambios necesarios.

Cualquier base de referencia de administración de la nube debe incluir un medio para programar, controlar y, posiblemente, automatizar las actualizaciones necesarias. Estas actualizaciones deben incluir como mínimo revisiones, pero también pueden incluir rendimiento, ajuste de tamaño y otros aspectos de la actualización de los recursos.

### <a name="remediation-automation"></a>Automatización de las correcciones

Como base de referencia mejorada para la administración de la nube, algunas cargas de trabajo pueden beneficiarse de la corrección automatizada. Cuando una carga de trabajo con frecuencia detecta problemas que no se pueden resolver mediante cambios de código o de arquitectura, la automatización de la corrección puede ayudar a reducir la carga de la administración de la nube para aumentar la satisfacción del usuario.

Muchos dirían que cualquier problema lo suficientemente común para automatizarse, debería solucionarse mediante la resolución de la deuda técnica. Cuando sea prudente una resolución a largo plazo, esta debe ser la opción predeterminada. Sin embargo, varios escenarios empresariales dificultan la justificación de grandes inversiones en la resolución de la deuda técnica. Cuando no se puede justificar esta resolución, pero la corrección es una carga común y costosa, la corrección automatizada es la siguiente mejor solución.

## <a name="next-steps"></a>Pasos siguientes

[Protección y recuperación](./protect.md), esas son las siguientes áreas que se deben considerarse en una base de referencia para la administración de la nube.

> [!div class="nextstepaction"]
> [Protección y recuperación](./protect.md)
