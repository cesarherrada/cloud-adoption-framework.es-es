---
title: 'Importancia crítica para la empresa: administración y operaciones de la nube'
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: 'Importancia crítica para la empresa: administración y operaciones de la nube'
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.openlocfilehash: be5cc97c7b42eb79f0ec9721376524dc2710e2c4
ms.sourcegitcommit: f3371811a36e12533ecbc3aa936e2a68e0cee25f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2019
ms.locfileid: "72683631"
---
# <a name="business-impact-in-cloud-management"></a>Efecto empresarial en la administración de la nube

Presuponga lo mejor y prepárese para lo peor. En la administración de TI es seguro presuponer que las cargas de trabajo necesarias para admitir las operaciones empresariales estarán disponibles y se realizarán según el acuerdo en cuanto a las restricciones, en función de la importancia seleccionada. Sin embargo, para administrar las inversiones de forma inteligente, es importante comprender el efecto sobre la empresa cuando se produce una interrupción o una degradación del rendimiento. Esta importancia se ilustra en el siguiente gráfico, que asigna posibles interrupciones empresariales de cargas de trabajo específicas al efecto empresarial de las interrupciones en una escala de valor relativa.

![Efecto de las interrupciones en el negocio](../../_images/manage/time-value-impact.png)

Para crear una base justa de comparación para el efecto sobre varias cargas de trabajo de una cartera, se sugiere una métrica de tiempo/valor. La métrica de tiempo/valor captura el efecto adverso de una interrupción en la carga de trabajo. Por lo general, este efecto se registra como una pérdida directa de ingresos o ingresos operativos durante un período de interrupción típico. Más concretamente, se calcula la pérdida de ingresos por unidad de tiempo. La métrica más común de tiempo/valor es el "efecto por hora", que mide las pérdidas de ingresos operativos por hora de interrupción.

Existen varios enfoques que se pueden usar para calcular el efecto. Cualquiera de las opciones de las secciones siguientes se puede aprovechar con resultados similares. Es importante usar el mismo enfoque para cada carga de trabajo al calcular las pérdidas protegidas en una cartera.

## <a name="start-with-estimates"></a>Comienzo con estimaciones

Los modelos operativos actuales pueden dificultar la determinación precisa del efecto. Afortunadamente, pocos sistemas necesitan gran precisión en el cálculo de las pérdidas. En el paso anterior de clasificación de la importancia, se sugirió que todas las cargas de trabajo se comenzaran por un valor predeterminado de "importancia media". Por lo general, las cargas de trabajo de importancia media reciben un nivel estándar de soporte de administración con un efecto relativamente reducido sobre los costos operativos. Solo cuando una carga de trabajo requiere recursos adicionales de administración operativa, se necesita mayor precisión en el efecto financiero.

En todas las cargas de trabajo estandarizadas, el efecto empresarial sirve como variable de priorización a la hora de recuperar sistemas durante una interrupción. Aparte esas situaciones limitadas, el efecto empresarial supondrá poco o ningún cambio en la experiencia de administración de las operaciones. 

## <a name="calculating-time"></a>Cálculo del tiempo

En función de la naturaleza de la carga de trabajo, las pérdidas se pueden calcular de una forma u otra. En el caso de los sistemas transaccionales de alto ritmo, como una plataforma comercial en tiempo real, las pérdidas por milisegundo pueden ser significativas. Los sistemas que se usan con menos frecuencia, como los de las nóminas, no se usan a todas horas. Es importante saber si la frecuencia de uso es alta o baja para normalizar la variable temporal al calcular el efecto financiero.

## <a name="calculating-total-impact"></a>Cálculo del efecto total

Cuando se desean inversiones de administración adicionales, la precisión del efecto empresarial resulta más importante. En las siguientes viñetas se describen los enfoques para calcular las pérdidas, del más preciso al menos preciso:

- **Pérdidas ajustadas**: si la empresa ha experimentado una pérdida importante en el pasado, como un huracán u otro desastre natural, con un ajuste de las notificaciones se pueden haber las pérdidas reales durante la interrupción. Estos cálculos se basan en los estándares del sector de los seguros para el cálculo de pérdidas y la administración de riesgos. El uso de pérdidas ajustadas como total de pérdidas en un período de tiempo específico puede generar proyecciones muy precisas.

- **Historial de pérdidas**: si el entorno local ha sufrido interrupciones en el pasado por inestabilidad de la infraestructura, puede ser un poco más difícil calcular las pérdidas. Sin embargo, las fórmulas de ajuste se siguen pudiendo aprovechar internamente. Para calcular el historial de pérdidas, compare las diferencias en las ventas, los ingresos brutos y los costos operativos en tres intervalos de tiempo: antes, durante y después de la interrupción. Al examinar estas diferencias se pueden identificar las pérdidas exactas cuando no hay otros datos disponibles.

- **Cálculo de pérdidas totales:** si no hay historial de datos disponible, se puede derivar un valor de pérdida comparativo. En este modelo se determina el promedio de ingresos brutos por hora para la unidad de negocio. Presuponer que una interrupción completa del sistema equivale al 100 % de la pérdida de ingresos es una mala suposición al proyectar inversiones con prevención de pérdidas. Sin embargo, se puede usar como base para comparar los efectos de las pérdidas y priorizar las inversiones.

Antes de realizar suposiciones con respecto a los cálculos de pérdidas, trabaje con el departamento financiero para determinar el mejor enfoque para calcular posibles pérdidas asociadas a una interrupción en la carga de trabajo.

## <a name="calculating-workload-impact"></a>Cálculo del efecto de la carga de trabajo

Al aprovechar el historial de datos para calcular las pérdidas, puede haber suficiente información para determinar claramente el efecto de cada carga de trabajo sobre esas pérdidas. Esta evaluación es donde la asociación con la empresa es absolutamente crítica. Una vez calculado el efecto total, debe atribuirse a cada carga de trabajo. Esa distribución del efecto debe provenir de las partes interesadas de la empresa, que deben estar de acuerdo en el efecto relativo y acumulativo de cada carga de trabajo. Además, el equipo debe solicitar comentarios de los ejecutivos la empresa para validar la alineación. Desafortunadamente, el resultado final es sentimiento y experiencia sobre el tema a partes iguales. La importancia de este ejercicio es que representa la lógica y las creencias de las partes interesadas de la empresa, quienes deben tener algo que decir sobre la asignación del presupuesto.

## <a name="using-the-template"></a>Uso de la plantilla

Los siguientes pasos se aplican a los lectores que utilizan el [libro de administración de las operaciones](https://raw.githubusercontent.com/microsoft/CloudAdoptionFramework/master/manage/opsmanagementworkbook.xlsx) para planear la administración de la nube.

1. La empresa debe actualizar el "ejemplo" o la "plantilla limpia" con el "tiempo/valor del efecto" de cada carga de trabajo. De forma predeterminada, el "tiempo/valor del efecto" representa las pérdidas proyectadas por hora asociadas con una interrupción en la carga de trabajo.

## <a name="next-steps"></a>Pasos siguientes

Una vez definido el efecto, [se pueden alinear los compromisos](./commitment.md).

> [!div class="nextstepaction"]
> [Alineación de los compromisos de administración con la empresa](./commitment.md)
