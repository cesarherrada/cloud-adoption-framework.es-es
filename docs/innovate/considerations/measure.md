---
title: 'Innovación en la nube: Measure'
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: 'Introducción al contenido de la innovación en la nube: medida'
author: BrianBlanchard
ms.author: brblanch
ms.date: 09/27/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: innovate
ms.openlocfilehash: 00928171c3bfba1638a7e8e43ea08df4745754d2
ms.sourcegitcommit: 35c162d2d09ec1c4a57d3d57a5db1d56ee883806
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72558438"
---
# <a name="measure-for-customer-impact"></a>Medida del impacto en los clientes

Hay varias maneras de medir el impacto en los clientes. Este artículo le ayudará a definir medidas que pueden ayudarle a validar las hipótesis creadas al intentar [crear con la empatía de los clientes](./build.md).

## <a name="strategic-metrics"></a>Métricas estratégicas

Durante la [fase de estrategia](../../strategy/index.md) del ciclo de vida de la adopción de la nube, se guía a los lectores a través de la creación y la documentación de las [motivaciones](../../strategy/motivations.md) y los [resultados empresariales](../../strategy/business-outcomes/index.md). Estos ejercicios proporcionan un conjunto de métricas que se pueden usar como prueba del impacto en el cliente. Cuando la innovación sea correcta, generará resultados alineados con los objetivos de la estrategia.

Antes de establecer métricas de aprendizaje, defina un pequeño número de métricas estratégicas a las que se espera que afecte esta innovación. Por lo general, las métricas estratégicas se alinearán con una o varias de las siguientes áreas de resultados: La [agilidad empresarial](../../strategy/business-outcomes/agility-outcomes.md), la [involucración del cliente](../../strategy/business-outcomes/engagement-outcomes.md), la [cobertura del cliente](../../strategy/business-outcomes/reach-outcomes.md), el [impacto financiero](../../strategy/business-outcomes/fiscal-outcomes.md) o, en el caso de la innovación operativa: el [rendimiento de la solución](../../strategy/business-outcomes/fiscal-outcomes.md).

Documente las métricas acordadas y realice el seguimiento del impacto con frecuencia. Sin embargo, no espere resultados de ninguna de estas métricas durante varias iteraciones. Consulte el [compromiso con la iteración](./index.md#commitment-to-iteration) para alinear las expectativas.

Aparte de la motivación y las métricas de los resultados empresariales, el resto de este artículo se centrará en las métricas de aprendizaje diseñadas como guía para la detección transparente y las iteraciones centradas en el cliente. Consulte el [compromiso con la transparencia](./index.md#commitment-to-transparency) para alinear las expectativas.

## <a name="learning-metrics"></a>Métricas de aprendizaje

Cuando se comparte con los clientes la primera versión de un producto viable mínimo (MVP), preferiblemente al final de la primera iteración de desarrollo, no habrá ningún impacto en las métricas estratégicas. Después de varias iteraciones, es posible que el equipo todavía esté lidiando para cambiar los comportamientos lo suficiente para impactar de manera significativa en las métricas estratégicas. Durante los procesos de aprendizaje, como los ciclos de crear-medir-aprender, se recomienda que el equipo adopte métricas de aprendizaje. Es más fácil realizar el seguimiento de estas métricas y aprovecharlas en oportunidades de aprendizaje.

### <a name="customer-flow-and-learning-metrics"></a>Métricas de flujo y aprendizaje del cliente

Si una solución de MVP valida una hipótesis centrada en el cliente, la solución impulsará algún cambio en los comportamientos de los clientes. Estos comportamientos en varias cohortes de clientes producirán resultados empresariales. Afortunadamente, cambiar los comportamientos de los clientes suele ser un proceso de varios pasos. Cada paso proporciona una oportunidad para medir el impacto, por lo que el equipo de adopción puede aprender y crear una solución mejor.

El aprendizaje de los cambios en los comportamientos del cliente se inicia asignando el flujo deseado creado por una solución de MVP.

![Flujo de cliente usado para determinar las métricas de aprendizaje](../../_images/innovate/customer-flow-learning-metrics.png)

En la mayoría de los casos, un flujo de cliente tendrá un punto de inicio fácil de definir y no más de dos puntos finales. Entre los puntos inicial y final se encuentran varias métricas de aprendizaje que se usarán como medidas en el bucle de comentarios:

1. **Punto inicial (desencadenador inicial):** El punto inicial es el escenario que desencadena la necesidad de esta solución. Cuando la solución se crea con la empatía de los clientes, ese desencadenador inicial debe animar al cliente a probar la solución MVP.
2. **Necesidad del cliente satisfecha:** La hipótesis se valida cuando una necesidad del cliente se satisface mediante la solución.
3. **Pasos de la solución:** Cada paso necesario para mover al cliente desde el desencadenador inicial hasta un resultado correcto es un paso de la solución. Cada paso genera una métrica de aprendizaje basada en las decisiones del cliente para pasar al siguiente paso.
4. **Adopción individual conseguida:** La próxima vez que se encuentre el desencadenador, si el cliente vuelve a la solución para satisfacer de nuevo la necesidad, se consigue la adopción individual.
5. **Indicador de resultados empresariales:** Cuando un cliente se comporta de una manera que contribuye positivamente al resultado de empresarial definido, se observa un indicador de resultado empresarial.
6. **Innovación verdadera:** Cuando los "indicadores de resultados empresariales" y la "adopción individual" se producen en la escala deseada, se ha experimentado una verdadera innovación.

Cada paso del flujo de cliente genera métricas de aprendizaje. Después de cada iteración (o versión), se prueba una nueva versión de la hipótesis. Al mismo tiempo, se prueban los retoques de la solución para reflejar los ajustes de la hipótesis. Cuando los clientes siguen el trazado prescrito en cualquier paso determinado, se registra una métrica positiva. Cuando los clientes se desvían del trazado prescrito para satisfacer sus necesidades, se registra una métrica negativa.

Estos contadores de alineación y desviación crean métricas de aprendizaje. Debe registrarse cada una de ellas y realizar su seguimiento a medida que el equipo de adopción de la nube progresa hacia la consecución de los resultados empresariales y la verdadera innovación. En el siguiente artículo de [aprendizaje con asociados cliente](./learn.md) analizaremos las maneras de aprovechar estas métricas para aprender y crear soluciones mejores.

### <a name="grouping-and-observing-customer-partners"></a>Agrupación y observación de los asociados cliente

La primera medida para definir las métricas de aprendizaje es la definición del asociado cliente. Cualquier cliente que participe en ciclos de innovación se califica como asociado cliente. Para medir el comportamiento con precisión, es importante definir los asociados cliente en un modelo de cohorte. En este modelo, se agrupan los clientes para comprender mejor cómo responden a cualquier cambio en el MVP. Los asociados cliente se agrupan normalmente en función de puntos de datos como los siguientes:

- **Grupo de experimento o enfoque:** Agrupación basada en la participación de los clientes en un experimento específico para probar los cambios durante un tiempo.
- **Segmento:** Agrupación de los clientes por el tamaño de la empresa.
- **Vertical:** Agrupación de los clientes por el sector vertical que representan.
- **Datos demográficos individuales:** Agrupación basada en datos demográficos personales, como la edad o la ubicación física.

Este tipo de agrupación permite la validación de las métricas de aprendizaje en varias secciones transversales de los clientes que deciden asociarse durante los esfuerzos de innovación. Todas las métricas posteriores deben observarse en función de una agrupación de clientes definible.

## <a name="next-steps"></a>Pasos siguientes

A medida que se acumulan métricas de aprendizaje, el equipo puede empezar a [aprender con los clientes](./learn.md).

> [!div class="nextstepaction"]
> [Aprender con los clientes](./learn.md)

Algunos de los conceptos de este artículo se basan en temas descritos en el libro [El método Lean Startup](http://theleanstartup.com/book), escrito por Eric Ries.
