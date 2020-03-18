---
title: Efecto empresarial en la administración de la nube
description: Use Cloud Adoption Framework para Azure para aprender a determinar y comprender el impacto que las interrupciones o la degradación del rendimiento pueden tener en su negocio.
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.openlocfilehash: bdd45861141b8fe69f8c13a49bdb6d387acd12ba
ms.sourcegitcommit: 0ea426f2f471eb7310c6f09478be1306cf7bf0d8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2020
ms.locfileid: "78341188"
---
# <a name="business-impact-in-cloud-management"></a>Efecto empresarial en la administración de la nube

Presuponga lo mejor y prepárese para lo peor. En la administración de TI es seguro presuponer que las cargas de trabajo necesarias para admitir las operaciones empresariales estarán disponibles y se realizarán según el acuerdo en cuanto a las restricciones, en función de la importancia seleccionada. Sin embargo, para administrar las inversiones de forma inteligente, es importante comprender el impacto en la empresa cuando se produce una interrupción o una degradación del rendimiento. Esta importancia se ilustra en el siguiente gráfico, que asigna posibles interrupciones empresariales de cargas de trabajo específicas al impacto empresarial de las interrupciones en una escala de valor relativa.

![Efecto de las interrupciones en el negocio](../../_images/manage/time-value-impact.png)

Para crear una base justa de comparación para el impacto sobre varias cargas de trabajo en una cartera, se sugiere una métrica de tiempo/valor. La métrica de tiempo/valor captura el impacto negativo de una interrupción en la carga de trabajo. Por lo general, este efecto se registra como una pérdida directa de ingresos o ingresos operativos durante un período de interrupción típico. Más concretamente, calcula la pérdida de ingresos por unidad de tiempo. La métrica más común de tiempo/valor es el *impacto por hora*, que mide las pérdidas de ingresos operativos por hora de interrupción.

Se pueden utilizar varios enfoques para calcular el impacto. Puede aplicar cualquiera de las opciones de las secciones siguientes para lograr resultados similares. Es importante usar el mismo enfoque para cada carga de trabajo al calcular las pérdidas protegidas en una cartera.

## <a name="start-with-estimates"></a>Comienzo con estimaciones

Los modelos operativos actuales pueden dificultar la determinación precisa del impacto. Afortunadamente, pocos sistemas necesitan gran precisión en el cálculo de las pérdidas. En el paso de *clasificación de la importancia* anterior, se sugirió que todas las cargas de trabajo se comenzaran por un valor predeterminado de *importancia media*. Por lo general, las cargas de trabajo de importancia media reciben un nivel estándar de soporte de administración con un impacto relativamente reducido sobre los costos operativos. Solo cuando una carga de trabajo requiere recursos adicionales de administración operativa, puede requerir un impacto financiero preciso.

En todas las cargas de trabajo estandarizadas, el impacto empresarial sirve como variable de priorización a la hora de recuperar sistemas durante una interrupción. Aparte esas situaciones limitadas, el impacto empresarial supone poco o ningún cambio en la experiencia de administración de las operaciones.

## <a name="calculate-time"></a>Cálculo del tiempo

En función de la naturaleza de la carga de trabajo, las pérdidas se pueden calcular de forma diferente. En el caso de los sistemas transaccionales de alto ritmo, como una plataforma comercial en tiempo real, las pérdidas por milisegundo pueden ser significativas. Es posible que los sistemas que se usan con menos frecuencia, como los de nóminas, no se utilicen a todas horas. Es importante saber si la frecuencia de uso es alta o baja para normalizar la variable temporal al calcular el impacto financiero.

## <a name="calculate-total-impact"></a>Cálculo del impacto total

Cuando se quieren considerar inversiones de administración adicionales, es más importante que el impacto empresarial sea más preciso. Los tres enfoques siguientes para calcular las pérdidas están ordenados del más al menos preciso:

- **Pérdidas ajustadas**: si la empresa ha experimentado un suceso con pérdidas importantes en el pasado, como un huracán u otro desastre natural, un ajuste de las notificaciones puede haber calculado las pérdidas reales durante la interrupción. Estos cálculos se basan en los estándares del sector de los seguros para el cálculo de pérdidas y la administración de riesgos. El uso de pérdidas ajustadas como total de pérdidas en un período de tiempo específico puede generar proyecciones muy precisas.

- **Historial de pérdidas**: si su entorno local ha sufrido interrupciones en el pasado por inestabilidad de la infraestructura, puede ser un poco más difícil calcular las pérdidas. Sin embargo, puede seguir aplicando las fórmulas de ajuste que se usan internamente. Para calcular el historial de pérdidas, compare las diferencias en las ventas, los ingresos brutos y los costos operativos en tres intervalos de tiempo: antes, durante y después de la interrupción. Al examinar estas diferencias se pueden identificar las pérdidas exactas cuando no hay otros datos disponibles.

- **Cálculo de pérdidas totales:** si no hay historial de datos disponible, puede derivar un valor de pérdida comparativo. En este modelo se determina el promedio de ingresos brutos por hora de la unidad de negocio. Cuando proyecta inversiones en prevención de pérdidas, no es justo suponer que una interrupción completa del sistema equivale a una pérdida del 100 % de los ingresos. Sin embargo, puede usar esta suposición como base para comparar el impacto de las pérdidas y priorizar las inversiones.

Antes de realizar determinadas suposiciones sobre posibles pérdidas asociadas a interrupciones de la carga de trabajo, se recomienda trabajar con el departamento financiero para determinar el mejor enfoque para realizar estos cálculos.

## <a name="calculate-workload-impact"></a>Cálculo del impacto de la carga de trabajo

Al calcular las pérdidas mediante la aplicación de datos históricos, puede tener información suficiente para determinar con claridad la contribución de cada carga de trabajo a esas pérdidas. En la realización de esta evaluación es donde las asociaciones dentro la empresa son absolutamente fundamentales. Una vez calculado el impacto total, este debe atribuirse en cada una de las cargas de trabajo. Esa distribución del efecto debe provenir de las partes interesadas de la empresa, que deben estar de acuerdo en el efecto relativo y acumulativo de cada carga de trabajo. Con ese objetivo, el equipo debe solicitar comentarios de los ejecutivos de la empresa para validar la alineación. Estos comentarios suelen ser sentimiento y experiencia en el tema a partes iguales. Es importante que este ejercicio represente la lógica y las creencias de las partes interesadas de la empresa, quienes deben tener algo que decir sobre la asignación del presupuesto.

## <a name="use-the-template"></a>Uso de la plantilla

Si utiliza el [libro de administración de las operaciones](https://raw.githubusercontent.com/microsoft/CloudAdoptionFramework/master/manage/opsmanagementworkbook.xlsx) para planear la administración de la nube, considere la posibilidad de realizar los pasos siguientes:

- Cada empresa debe actualizar todas las cargas de trabajo del *ejemplo* o la *plantilla limpia* con el *tiempo/valor del efecto* de cada carga de trabajo. De forma predeterminada, el *tiempo/valor del efecto* representa las pérdidas proyectadas por hora asociadas con una interrupción en la carga de trabajo.

## <a name="next-steps"></a>Pasos siguientes

Una vez que la empresa haya definido el impacto, puede [alinear los compromisos](./commitment.md).

> [!div class="nextstepaction"]
> [Alineación de los compromisos de administración con la empresa](./commitment.md)
