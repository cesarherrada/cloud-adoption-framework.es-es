---
title: 'Innovación en la nube: Predicción e influencia'
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: 'Introducción a la innovación en la nube: Predicción e influencia'
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: innovate
ms.openlocfilehash: e6187bc926aacd9a09e67b8cd2bfe94e5a4a42dd
ms.sourcegitcommit: f3371811a36e12533ecbc3aa936e2a68e0cee25f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2019
ms.locfileid: "72682626"
---
# <a name="predict-and-influence"></a>Predicción e influencia

Hay dos clases de aplicaciones en la economía digital: históricas y predictivas. Muchas de las necesidades de los clientes se pueden satisfacer únicamente mediante el uso de datos históricos, incluidos los datos casi en tiempo real. En este momento, la mayoría de las soluciones se centran principalmente en la agregación de datos. Después, procesan y comparten los datos de nuevo con el cliente, en forma de experiencia digital o sobre el terreno.

Como el modelado predictivo resulta más rentable y está disponible, las experiencias de búsqueda anticipada de la demanda de los clientes llevan a mejores decisiones y acciones. Sin embargo, esa demanda no siempre tiene que conducir a una solución predictiva. En la mayoría de los escenarios, una vista de los datos históricos puede proporcionar información suficiente para permitir al cliente tomar una decisión por sí mismo.

Por desgracia, los clientes suelen tener una falta de visión que conduce a tomar decisiones en función de su entorno inmediato y de su esfera de influencia. A medida que las opciones y las decisiones crecen en número y consecuencias, es posible que esta falta de visión conduzca a no satisfacer las necesidades de los clientes. Al mismo tiempo, cuando se demuestra una hipótesis a escala, la empresa que proporciona la solución puede comprender miles o millones de decisiones de los clientes. Es posible considerar los patrones y sus efectos. La funcionalidad de predicción es una inversión razonable siempre que sea necesario conocer esos patrones para tomar decisiones que satisfagan las necesidades de los clientes.

## <a name="examples-of-predictions-and-influence"></a>Ejemplos de predicciones e influencia

El uso de datos para realizar predicciones puede verse en varias aplicaciones y experiencias sobre el terreno.

- **Comercio electrónico:** los elementos sugeridos son un ejemplo de predicción. En función de lo que otros usuarios hayan adquirido juntos, el sitio web puede sugerir productos que puede merecer la pena agregar al carro.
- **Realidad ajustada:** IoT ofrece ejemplos más avanzados. Un dispositivo en una línea de ensamblado detecta un aumento de la temperatura de las máquinas. Un modelo predictivo basado en la nube determina cómo responder. En función de esa predicción, se indica a otro dispositivo que ralentice la línea de montaje hasta que la máquina se enfríe.
- **Productos de consumo:** los teléfonos móviles, las casas inteligentes, incluso el automóvil, contienen cierto grado de funcionalidades predictivas al sugerir actividades basadas en factores como la ubicación o la hora del día. Cuando se alinean la predicción y la hipótesis inicial, esas predicciones influyen en los comportamientos. Cuando ambas están en una fase muy madura, la predicción conduce a la acción como, por ejemplo, en un automóvil que se desplaza sin conductor.

## <a name="developing-predictive-capabilities"></a>Desarrollo de funcionalidades predictivas

Las soluciones que proporcionan constantemente funciones de predicción precisas suelen incluir cinco características principales: datos, información detallada, patrones, predicciones e interacciones. Cada una es necesaria para desarrollar las funcionalidades de predicción. Al igual que todas las grandes innovaciones, el desarrollo de funcionalidades predictivas requerirá un [compromiso con la iteración](./index.md#commitment-to-iteration). En cada iteración, una o varias de las siguientes características se deben consolidar para comprobar hipótesis de clientes cada vez más complejas.

![Pasos para las funcionalidades predictivas](../../_images/innovate/predict-and-influence.png)

> [!CAUTION]
> Si la hipótesis del cliente desarrollada a partir del artículo sobre la [creación con empatía de los clientes](./build.md) incluye funcionalidades de predicción, puede que este artículo sea aplicable. Sin embargo, las funcionalidades predictivas requieren una gran inversión de tiempo y energía. Cuando las funcionalidades predictivas constituyen [demandas técnicas](./build.md#reduce-complexity-and-delay-technical-spikes) en lugar de una posible fuente de valor para el cliente, se recomienda retrasar las predicciones hasta que se hayan comprobado las hipótesis de los clientes a escala.

## <a name="data"></a>Datos

La característica más sencilla de las anteriores son los datos. Cada una de las materias anteriores para desarrollar invenciones digitales generará datos. Esos datos pueden contribuir al desarrollo de predicciones. Para más información sobre las formas de obtener datos en una solución predictiva, consulte los artículos sobre la [democratización de los datos](./data.md) o la [interacción con los dispositivos](./devices.md).

Se puede usar una serie de orígenes de datos para proporcionar funcionalidades de predicción:

## <a name="insights"></a>Información detallada

Los expertos en la materia aprovechan los datos sobre las necesidades y los comportamientos de los clientes para desarrollar información detallada empresarial básica a partir de un estudio de los datos sin procesar. Esta información detallada puede identificar los casos de comportamientos deseados de los clientes (o, por el contrario, los resultados no deseados). Durante las iteraciones en las predicciones, esta información detallada puede ayudar a identificar posibles correlaciones, lo que podría tener un efecto causal en los resultados positivos. Para conocer algunas orientaciones sobre cómo permitir que los expertos en la materia lleguen a conclusiones, consulte el artículo sobre la [democratización de los datos](./data.md).

## <a name="patterns"></a>Patrones

Los usuarios suelen tener dificultades inherentes con la detección de patrones en grandes volúmenes de datos. Los equipos informáticos se diseñaron para ese propósito. El aprendizaje automático agiliza este propósito mediante la detección de patrones en una gran cantidad de datos, lo que se conoce un modelo de aprendizaje automático. A continuación, estos patrones se aplican mediante algoritmos de aprendizaje automático para predecir lo que ocurrirá cuando se especifique un nuevo conjunto de puntos de datos en los algoritmos.

Mediante el uso de conclusiones como punto de partida, el aprendizaje automático entrena y aplica modelos de predicción a los datos para aprovechar los patrones de estos. Tras varias iteraciones de entrenamiento, prueba y adopción, estos modelos y algoritmos pueden predecir con precisión los resultados futuros.

[Azure Machine Learning Service](https://docs.microsoft.com/azure/machine-learning/service/overview-what-is-azure-ml) es la herramienta nativa en la nube de Azure para la creación y el entrenamiento de modelos basados en los datos. Esta herramienta también incluye un [flujo de trabajo para acelerar el desarrollo de algoritmos de aprendizaje automático](https://docs.microsoft.com/azure/machine-learning/service/concept-azure-machine-learning-architecture). Este flujo de trabajo se puede usar para desarrollar algoritmos mediante la interfaz visual o Python.

En el caso de los modelos de aprendizaje automático más sólidos, los [servicios de aprendizaje automático de Azure HDInsight](https://docs.microsoft.com/azure/hdinsight/r-server/r-server-overview) proporcionan una plataforma de aprendizaje automático basada en clústeres de Apache Hadoop. Este enfoque permite un control más pormenorizado de los clústeres subyacentes, el almacenamiento y los nodos de proceso. El uso de Azure HDInsight también proporciona una integración más avanzada mediante herramientas como ScaleR y SparkR para crear predicciones basadas en datos integrados e ingeridos, incluso con datos de una secuencia. La [solución de predicción de retrasos de vuelos](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-r-scaler-sparkr) muestra cada una de estas funcionalidades avanzadas para predecir retrasos de vuelo en función de las condiciones meteorológicas. La solución de HDInsight también permite controles empresariales, como la seguridad de los datos, el acceso a la red y la supervisión del rendimiento para la puesta en marcha de patrones.

## <a name="predictions"></a>Predicciones

Una vez que se ha creado y entrenado un patrón, se puede aplicar mediante el uso de API, que pueden realizar predicciones durante el desarrollo de una experiencia digital. La mayoría de estas API se crean a partir de un modelo bien entrenado basado en un patrón dentro de los datos. Sin embargo, a medida que más clientes implementan cargas de trabajo comunes en la nube, los proveedores de nube pueden proporcionar API comunes de predicción que permitan una adopción más rápida de las predicciones.

[Azure Cognitive Services](https://docs.microsoft.com/azure/cognitive-services) es un ejemplo de una compilación de API predictiva por parte de un proveedor de la nube. Este servicio incluye API predictivas para la moderación de contenido, la detección de anomalías o sugerencias para personalizar el contenido. Estas API están preparadas para usarse en función de los patrones de contenido comunes que Microsoft ha usado para entrenar los modelos. Cada una de esas API realiza predicciones basadas en los datos que se alimentan en la API.

[Azure Machine Learning Service](https://docs.microsoft.com/azure/machine-learning) permite la implementación de algoritmos personalizados, que se pueden crear y entrenar únicamente con sus propios datos. Puede obtener más información sobre la implementación de predicciones con Azure Machine Learning [aquí](https://docs.microsoft.com/azure/machine-learning/service/how-to-deploy-and-where).

En el artículo sobre [configuración de clústeres de HDInsight](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-provision-linux-clusters) se describen los procesos para exponer las predicciones desarrolladas para ML Services en Azure HDInsight.

## <a name="interactions"></a>Interacciones

Una vez que una predicción está disponible mediante una API, se puede usar para influir en los comportamientos de los clientes. Esa influencia se produce en forma de interacciones. Una interacción con un algoritmo de aprendizaje automático se produce dentro de las otras experiencias digitales o ambientales. A medida que los datos se recopilan a través de la aplicación o la experiencia, se ejecutan mediante los algoritmos de aprendizaje automático. Cuando el algoritmo predice un resultado, la predicción se puede volver a compartir con el cliente mediante la experiencia actual.

Obtenga más información sobre las interacciones en una [solución de realidad ajustada](./devices.md#adjusted-reality) para más detalles sobre cómo crear una interacción dentro de una experiencia sobre el terreno.

## <a name="next-steps"></a>Pasos siguientes

En función de los conocimientos adquiridos con respecto a las [materias de innovación](./invention.md), dentro de la [metodología de innovación](./index.md) sabe que dispone de las herramientas técnicas necesarias para [crear con empatía](./build.md).

> [!div class="nextstepaction"]
> [Crear con empatía](./build.md)
