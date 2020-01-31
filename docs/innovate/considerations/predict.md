---
title: 'Innovación en la nube: Predicción e influencia'
description: 'Introducción a la innovación en la nube: Predicción e influencia'
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: innovate
ms.openlocfilehash: f55325b46ee9b2e45dd539c08f426d49357f5ba3
ms.sourcegitcommit: 2362fb3154a91aa421224ffdb2cc632d982b129b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76808403"
---
# <a name="predict-and-influence"></a>Predicción e influencia

Hay dos clases de aplicaciones en la economía digital: *históricas* y *predictivas*. Muchas de las necesidades de los clientes se pueden satisfacer únicamente mediante el uso de datos históricos, incluidos los datos casi en tiempo real. En este momento, la mayoría de las soluciones se centran principalmente en la agregación de datos. Después, procesan y comparten los datos de nuevo con el cliente, en forma de experiencia digital o sobre el terreno.

A medida que el modelado predictivo es más rentable y está disponible fácilmente, los clientes exigen experiencias avanzadas que les lleven a mejores decisiones y acciones. Sin embargo, esa demanda no siempre sugiere una solución predictiva. En la mayoría de los escenarios, una vista de los datos históricos puede proporcionar información suficiente para permitir al cliente tomar una decisión por sí mismo.

Por desgracia, los clientes suelen tener una falta de visión que conduce a tomar decisiones en función de su entorno inmediato y de su esfera de influencia. A medida que las opciones y las decisiones crecen en número y consecuencias, es posible que esta falta de visión no satisfaga las necesidades de los clientes. Al mismo tiempo, cuando se demuestra una hipótesis a escala, la empresa que proporciona la solución puede comprender miles o millones de decisiones de los clientes. Este enfoque general permite ver patrones amplios, así como el impacto que tienen. La funcionalidad de predicción es una inversión razonable cuando es necesario comprender esos patrones para tomar las decisiones más acertadas para el cliente.

## <a name="examples-of-predictions-and-influence"></a>Ejemplos de predicciones e influencia

Diversas aplicaciones y experiencias ambientales usan datos para realizar predicciones:

- **Comercio electrónico:** en función de lo que otros consumidores similares hayan adquirido, un sitio web de comercio electrónico sugiere productos que puede merecer la pena agregar al carro.
- **Realidad ajustada:** IoT ofrece instancias más avanzadas de funcionalidad predictiva. Por ejemplo, un dispositivo en una línea de ensamblado detecta un aumento de la temperatura de una máquina. Un modelo predictivo basado en la nube determina cómo responder. En función de esa predicción, otro dispositivo ralentiza la línea de montaje hasta que la máquina se enfría.
- **Productos de consumo:** los teléfonos móviles, las casas inteligentes, incluso el automóvil, usan funcionalidades predictivas, que emplean para que sugieran el comportamiento del usuario en función de factores como la ubicación o la hora del día. Cuando la predicción y la hipótesis inicial se alinean, la predicción conduce a la acción. En una fase muy avanzada, esta alineación puede hacer que productos, como un vehículo autónomo, sean una realidad.

## <a name="develop-predictive-capabilities"></a>Desarrollo de funcionalidades predictivas

Las soluciones que proporcionan constantemente funcionalidades de predicción precisas suelen incluir cinco características principales: *datos*, *conclusiones*, *patrones*, *predicciones* e *interacciones*. Cada aspecto es necesario para desarrollar las funcionalidades predictivas. Al igual que todas las grandes innovaciones, el desarrollo de funcionalidades predictivas requiere un [compromiso con la iteración](./index.md#commitment-to-iteration). En cada iteración, una o varias de las siguientes características se consolidan para comprobar hipótesis de clientes cada vez más complejas.

![Pasos para las funcionalidades predictivas](../../_images/innovate/predict-and-influence.png)

> [!CAUTION]
> Si la hipótesis del cliente desarrollada en [Creación con la empatía de los clientes](./build.md) incluye funcionalidades predictivas, puede que se apliquen los principios descritos. Sin embargo, las funcionalidades predictivas requieren una gran inversión de tiempo y energía. Cuando las funcionalidades predictivas constituyen [demandas técnicas](./build.md#reduce-complexity-and-delay-technical-spikes) en lugar de una posible fuente de valor para el cliente, se recomienda retrasar las predicciones hasta que se hayan comprobado las hipótesis de los clientes a escala.

## <a name="data"></a>data

Los datos son el componente más elemental de las características mencionadas anteriormente. Cada una de las materias para desarrollar invenciones digitales genera datos. Ciertamente, esos datos contribuyen al desarrollo de predicciones. Para más información sobre las formas de obtener datos en una solución predictiva, consulte [Democratización de los datos](./data.md) e [Interacción con dispositivos](./devices.md).

Se puede usar una variedad de orígenes de datos para proporcionar funcionalidades predictivas:

## <a name="insights"></a>Información detallada

Los expertos en la materia usan los datos sobre las necesidades y comportamientos de los clientes para desarrollar conclusiones empresariales básicas a partir de un estudio de datos sin procesar. Esta información detallada puede identificar los casos de comportamientos deseados de los clientes (o, por el contrario, los resultados no deseados). Durante las iteraciones en las predicciones, esta información detallada puede ayudar a identificar posibles correlaciones, lo que finalmente podría generar resultados positivos. Para obtener información sobre cómo permitir que los expertos en la materia elaboren conclusiones, consulte [Democratización de los datos](./data.md).

## <a name="patterns"></a>Patrones

Las personas siempre han intentado detectar patrones en grandes volúmenes de datos. Los equipos informáticos se diseñaron para ese propósito. La solución Machine Learning acelera esta misión mediante la detección precisa de dichos patrones, una aptitud que comprende el modelo de modelo de Machine Learning. A continuación, estos patrones se aplican mediante algoritmos de aprendizaje automático para predecir los resultados cuando se especifique un nuevo conjunto de puntos de datos en los algoritmos.

Usando las conclusiones como punto de partida, el aprendizaje automático desarrolla y aplica modelos predictivos para exprimir los patrones de datos. A través de varias iteraciones de entrenamiento, prueba y adopción, estos modelos y algoritmos pueden predecir con precisión los resultados futuros.

[Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/service/overview-what-is-azure-ml) es el servicio nativo en la nube de Azure para la creación y el entrenamiento de modelos basados en los datos. Esta herramienta también incluye un [flujo de trabajo para acelerar el desarrollo de algoritmos de aprendizaje automático](https://docs.microsoft.com/azure/machine-learning/service/concept-azure-machine-learning-architecture). Este flujo de trabajo se puede usar para desarrollar algoritmos mediante una interfaz visual o Python.

En el caso de los modelos de aprendizaje automático más sólidos, los [servicios de aprendizaje automático de Azure HDInsight](https://docs.microsoft.com/azure/hdinsight/r-server/r-server-overview) proporcionan una plataforma de aprendizaje automático basada en clústeres de Apache Hadoop. Este enfoque permite un control más pormenorizado de los clústeres subyacentes, el almacenamiento y los nodos de proceso. Azure HDInsight también proporciona una integración más avanzada mediante herramientas como ScaleR y SparkR para crear predicciones basadas en datos integrados e ingeridos, incluso con datos de una secuencia. La [solución de predicción de retrasos de vuelos](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-r-scaler-sparkr) muestra cada una de estas funcionalidades avanzadas cuando se usa para predecir retrasos de vuelos en función de las condiciones meteorológicas. La solución de HDInsight también permite controles empresariales, como la seguridad de los datos, el acceso a la red y la supervisión del rendimiento para la puesta en marcha de patrones.

## <a name="predictions"></a>Predicciones

Después de crear y entrenar un patrón, puede aplicarlo mediante las API, que pueden realizar predicciones durante la entrega de una experiencia digital. La mayoría de estas API se crean a partir de un modelo bien entrenado basado en un patrón de los datos. A medida que más clientes implementan las cargas de trabajo diarias en la nube, las API de predicción que usan los proveedores de la nube conducen a una adopción cada vez más rápida.

[Azure Cognitive Services](https://docs.microsoft.com/azure/cognitive-services) es un ejemplo de API predictiva creada por un proveedor de la nube. Este servicio incluye API predictivas para la moderación de contenido, la detección de anomalías y las sugerencias para personalizar el contenido. Estas API están preparadas para usar y se basan en patrones de contenido conocidos, que Microsoft ha usado para entrenar los modelos. Cada una de esas API realiza predicciones basadas en los datos que se introducen en la API.

[Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning) permite la implementación de algoritmos personalizados, que pueden crear y entrenar únicamente con sus propios datos. Obtenga más información sobre la implementación de predicciones con [Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/service/how-to-deploy-and-where).

En el artículo sobre la [configuración de clústeres en HDInsight](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-provision-linux-clusters) se describen los procesos para exponer las predicciones desarrolladas para ML Services en Azure HDInsight.

## <a name="interactions"></a>Interacciones

Una vez que una predicción está disponible a través de una API, se puede usar para influir en el comportamiento del cliente. Esa influencia se produce en forma de interacciones. Una interacción con un algoritmo de aprendizaje automático se produce dentro de las otras experiencias digitales o ambientales. A medida que se recopilan datos a través de la aplicación o la experiencia, se ejecutan mediante los algoritmos de aprendizaje automático. Cuando el algoritmo predice un resultado, la predicción se puede volver a compartir con el cliente mediante la experiencia actual.

Obtenga más información sobre cómo crear una experiencia ambiental a través de una [solución de realidad ajustada](./devices.md#adjusted-reality).

## <a name="next-steps"></a>Pasos siguientes

Una vez familiarizado con las [materias de invención](./invention.md) y la [metodología de innovación](./index.md), estará preparado para aprender a [crear con la empatía de los clientes](./build.md).

> [!div class="nextstepaction"]
> [Crear con empatía](./build.md)
