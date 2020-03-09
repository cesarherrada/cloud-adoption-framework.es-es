---
title: Medición del impacto en el cliente
description: Defina el flujo de cliente que prefiera y establezca métricas de aprendizaje para medir el comportamiento del cliente y el proceso de adopción.
author: BrianBlanchard
ms.author: brblanch
ms.date: 09/27/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: innovate
ms.openlocfilehash: 1b60f1b9cadb20ae516946fe09299fb3af2f895c
ms.sourcegitcommit: 10637acba8c857a6f5aa8c4a80c0649903f60402
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78171147"
---
# <a name="measure-for-customer-impact"></a>Medida del impacto en los clientes

Hay varias maneras de medir el impacto en los clientes. Este artículo le ayudará a definir métricas para validar las hipótesis que surgen de un trabajo para [crear con la empatía de los clientes](./build.md).

## <a name="strategic-metrics"></a>Métricas estratégicas

Durante la [fase de estrategia](../../strategy/index.md) del ciclo de vida de la adopción de la nube, examinamos [motivaciones](../../strategy/motivations.md) y [resultados empresariales](../../strategy/business-outcomes/index.md). Estas prácticas proporcionan un conjunto de métricas con las que probar el impacto para el cliente. Cuando la innovación sea correcta, tienden a mostrarse resultados que se alinean con sus objetivos estratégicos.

Antes de establecer métricas de aprendizaje, defina un pequeño número de métricas estratégicas a las que quiera que afecte esta innovación. Por lo general, esas métricas estratégicas se alinean con una o varias de las siguientes áreas de resultados: [agilidad empresarial](../../strategy/business-outcomes/agility-outcomes.md), [interacción con el cliente](../../strategy/business-outcomes/engagement-outcomes.md), [alcance de clientes](../../strategy/business-outcomes/reach-outcomes.md), [impacto financiero](../../strategy/business-outcomes/fiscal-outcomes.md) o, en el caso de la innovación operativa: [rendimiento de la solución](../../strategy/business-outcomes/fiscal-outcomes.md).

Documente las métricas acordadas y realice el seguimiento del impacto con frecuencia. Sin embargo, no espere resultados de ninguna de estas métricas durante varias iteraciones. Para obtener más información sobre cómo establecer y alinear las expectativas entre las partes implicadas, consulte [Compromiso con la iteración](./index.md#commitment-to-iteration).

Aparte de la motivación y las métricas de los resultados empresariales, el resto de este artículo se centra en las métricas de aprendizaje diseñadas como guía para la detección transparente y las iteraciones centradas en el cliente. Para obtener más información sobre estos aspectos, consulte [Compromiso con la transparencia](./index.md#commitment-to-transparency).

## <a name="learning-metrics"></a>Métricas de aprendizaje

Cuando se comparte con los clientes la primera versión de un producto viable mínimo (MVP), preferiblemente al final de la primera iteración de desarrollo, no habrá ningún impacto en las métricas estratégicas. Después de varias iteraciones, es posible que el equipo todavía esté lidiando para cambiar los comportamientos lo suficiente para que afecten de manera significativa a las métricas estratégicas. Durante los procesos de aprendizaje, como los ciclos de crear-medir-aprender, se recomienda que el equipo adopte métricas de aprendizaje. Estas miden las oportunidades de seguimiento y aprendizaje.

### <a name="customer-flow-and-learning-metrics"></a>Métricas de flujo y aprendizaje del cliente

Si una solución de MVP valida una hipótesis centrada en el cliente, la solución impulsará algún cambio en los comportamientos de los clientes. Estos cambios de comportamiento en los cohortes del cliente deben mejorar los resultados empresariales. Tenga en cuenta que el cambio en el comportamiento del cliente suele ser un proceso de varios pasos. Dado que cada paso proporciona una oportunidad para medir el impacto, el equipo de adopción puede aprender durante todo el proceso y crear una solución mejor.

El aprendizaje de los cambios en el comportamiento del cliente comienza con la asignación del flujo que espera ver de una solución de MVP.

![Flujo de cliente usado para determinar las métricas de aprendizaje](../../_images/innovate/customer-flow-learning-metrics.png)

En la mayoría de los casos, un flujo de cliente tendrá un punto de inicio fácil de definir y no más de dos puntos finales. Entre los puntos inicial y final se encuentran varias métricas de aprendizaje que se usarán como medidas en el bucle de comentarios:

1. **Punto inicial (desencadenador inicial):** el punto inicial es el escenario que desencadena la necesidad de esta solución. Cuando la solución se crea con la empatía de los clientes, ese desencadenador inicial debe animar al cliente a probar la solución MVP.
2. **Necesidad del cliente satisfecha:** La hipótesis se valida cuando una necesidad del cliente se satisface mediante la solución.
3. **Pasos de la solución:** este término hace referencia a los pasos necesarios para mover al cliente desde el desencadenador inicial hasta un resultado correcto. Cada paso genera una métrica de aprendizaje basada en la decisión del cliente para pasar al siguiente paso.
4. **Adopción individual conseguida:** la próxima vez que se encuentre el desencadenador, si el cliente vuelve a la solución para satisfacer su necesidad, se consigue la adopción individual.
5. **Indicador de resultados empresariales:** cuando un cliente se comporta de una manera que contribuye al resultado empresarial definido, se observa un indicador de resultado empresarial.
6. **Innovación verdadera:** cuando los *indicadores de resultados empresariales* y la *adopción individual* se producen en la escala deseada, se ha conseguido una verdadera innovación.

Cada paso del flujo de cliente genera métricas de aprendizaje. Después de cada iteración (o versión), se prueba una nueva versión de la hipótesis. Al mismo tiempo, se prueban los retoques de la solución para reflejar los ajustes de la hipótesis. Cuando los clientes siguen el trazado prescrito en cualquier paso determinado, se registra una métrica positiva. Cuando los clientes se desvían del trazado prescrito, se registra una métrica negativa.

Estos contadores de alineación y desviación crean métricas de aprendizaje. Es necesario registrarlas y realizar su seguimiento a medida que el equipo de adopción de la nube progresa hacia la consecución de los resultados empresariales y la verdadera innovación. En el apartado sobre el [aprendizaje con los clientes](./learn.md), analizaremos las maneras de aplicar estas métricas para aprender y crear soluciones mejores.

### <a name="grouping-and-observing-customer-partners"></a>Agrupación y observación de los asociados cliente

La primera medida para definir las métricas de aprendizaje es la definición del asociado cliente. Cualquier cliente que participe en ciclos de innovación se califica como asociado cliente. Para medir el comportamiento con precisión, debe utilizar un modelo de cohorte para definir los asociados cliente. En este modelo, los clientes se agrupan para mejorar la comprensión de sus respuestas a los cambios en el MVP. Estos grupos suelen ser similares a los siguientes:

- **Grupo de experimento o enfoque:** agrupación de clientes basada en su participación en un experimento específico diseñada probar los cambios con el tiempo.
- **Segmento:** Agrupación de los clientes por el tamaño de la empresa.
- **Vertical:** agrupación de clientes por el *sector vertical* que representan.
- **Datos demográficos individuales:** agrupación basada en datos demográficos personales, como la edad o la ubicación física.

Estos tipos de agrupaciones le ayudan a validar las métricas de aprendizaje en varias secciones transversales de los clientes que deciden asociarse usted durante los trabajos de innovación. Todas las métricas posteriores deben derivarse de la agrupación de clientes definible.

## <a name="next-steps"></a>Pasos siguientes

A medida que se acumulan métricas de aprendizaje, el equipo puede empezar a [aprender con los clientes](./learn.md).

> [!div class="nextstepaction"]
> [Aprender con los clientes](./learn.md)

Algunos de los conceptos de este artículo se basan en temas descritos en el libro [El método Lean Startup](http://theleanstartup.com/book), escrito por Eric Ries.
