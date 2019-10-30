---
title: 'Guía de innovación de Azure: Predicción e influencia'
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: Aprenda a predecir e influir con Azure.
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: innovate
ms.custom: fasttrack-edit, AQC
ms.localizationpriority: high
ms.openlocfilehash: b2ed1b072d5226649e5248e350edfa3578978c4c
ms.sourcegitcommit: 910efd3e686bd6b9bf93951d84253b43d4cc82b5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72769257"
---
::: zone target="docs"

# <a name="azure-innovation-guide-predict-and-influence"></a>Guía de innovación de Azure: Predicción e influencia

::: zone-end

::: zone target="chromeless"

# <a name="predict-and-influence"></a>Predicción e influencia

::: zone-end

Como innovador, su empresa tendrá información sobre los datos, el comportamiento y las necesidades de la base de clientes. Estudiar esta información puede ayudar a predecir las necesidades de los clientes, incluso antes de que se puedan dar cuenta de esas necesidades. En este artículo se presentan algunos enfoques para ofrecer soluciones predictivas. En la sección posterior, el artículo presenta enfoques para integrar dichas predicciones en la solución para influir en los comportamientos de los clientes.

La tabla siguiente está diseñada para ayudarle a encontrar la mejor solución en función de sus necesidades de implementación.

|Servicio  |Modelos pregenerados  |Compilación y experimento  |Entrenamiento y compilación con Python|Aptitudes necesarias|
|---------|---------|---------|---------|---------|
|Cognitive Services|Sí|No|Sin|Aptitudes de API y desarrolladores|
|Azure Machine Learning Studio|Sí|Sí|Sin|Descripción general de los algoritmos de predicción|
|Servicio Azure Machine Learning|Sí|Sí|Sí|Científico de datos|

## <a name="azure-cognitive-servicestabcognitiveservices"></a>[Azure Cognitive Services](#tab/CognitiveServices)

La ruta más rápida y más sencilla a las predicciones es Azure Cognitive Services. Cognitive Services permite realizar predicciones basadas en modelos existentes, que no requieren entrenamiento adicional. Estos servicios son óptimos cuando no hay un científico de datos entre el personal para entrenar el modelo predictivo. En algunos servicios, no se requiere ningún entrenamiento. Otros solo requieren un entrenamiento mínimo.

Para obtener una lista de los servicios disponibles y la cantidad de entrenamiento necesaria, consulte [Cognitive Services y Machine Learning](https://docs.microsoft.com/azure/cognitive-services/cognitive-services-and-machine-learning#service-requirements-for-the-data-model).

### <a name="action"></a>.

Para usar una API de Cognitive Services:

1. Vaya a **Cognitive Services**.
2. Haga clic en **Agregar +** para buscar una instancia de Cognitive Services desde Marketplace.
3. Si conoce el nombre del servicio que quiere usar, puede escribir dicho nombre en el cuadro de texto **Buscar en Marketplace**.
4. O bien, para obtener una lista de Cognitive Services, haga clic en el vínculo **Ver más** junto al encabezado de Cognitive Services.

::: zone target="chromeless"

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.CognitiveServices%2Faccounts]" submitText="Go to Cognitive Services" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

::: zone target="docs"

Vaya directamente a Cognitive Services en [Azure Portal](https://portal.azure.com/#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.CognitiveServices%2Faccounts).

::: zone-end

## <a name="azure-machine-learning-studiotabmachinelearningstudio"></a>[Azure Machine Learning Studio](#tab/MachineLearningStudio)

Si los modelos existentes dentro de Cognitive Services no se alinean con la predicción deseada, Azure Machine Learning Studio puede proporcionar una manera de compilar las predicciones deseadas, sin necesidad de conocimientos profundos de ciencia de datos.

<!-- markdownlint-disable MD024 -->

### <a name="action"></a>.

Puede usar un Azure Machine Learning Studio para compilar un modelo y experimentar con dicho modelo:

1. Vaya a **Azure Machine Learning Studio**.
2. Haga clic en **Creación y uso compartido de un área de trabajo de Azure Machine Learning Studio** y siga las indicaciones para crear un área de trabajo.
3. La nueva área de trabajo proporciona una interfaz de arrastrar y colocar para crear un modelo y experimentar con el modelo, como alternativa al entrenamiento profundo.

::: zone target="chromeless"

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.MachineLearning%2Fworkspaces]" submitText="Go to Azure Machine Learning Studio" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

::: zone target="docs"

Vaya directamente a Azure Machine Learning Studio en [Azure Portal](https://portal.azure.com/#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.MachineLearning%2Fworkspaces).

::: zone-end

## <a name="azure-machine-learning-servicetabmachinelearningservice"></a>[Servicio Azure Machine Learning](#tab/MachineLearningService)

Azure Machine Learning Service proporciona el enfoque más profundo basado en código necesario para un entrenamiento más profundo de los conjuntos de datos de los clientes. Mediante lenguajes como Python, los científicos de datos pueden entrenar y luego compilar un algoritmo para predecir las necesidades de los clientes.

### <a name="action"></a>.

Un científico de datos puede usar Azure Machine Learning Service para entrenar y compilar un modelo mediante lenguajes avanzados, como Python:

1. Vaya a **Azure Machine Learning Service**.
2. Haga clic en **Creación de áreas de trabajo de Machine Learning Service** y siga las indicaciones para crear un área de trabajo.
3. La nueva área de trabajo proporciona un enfoque controlado por código para que los científicos de datos entrenen y compilen modelos que requieren un análisis más avanzado con el fin de predecir con precisión las necesidades de los clientes.

::: zone target="chromeless"

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.MachineLearningServices%2Fworkspaces]" submitText="Go to Azure Machine Learning Service" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

::: zone target="docs"

Vaya directamente a Azure Machine Learning Studio en [Azure Portal](https://portal.azure.com/#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.MachineLearningServices%2Fworkspaces).

::: zone-end

## <a name="influence"></a>Influencia

Todos los métodos mencionados anteriormente dan como resultado una API que expone el modelo de predicción a las aplicaciones. Dentro de la solución, use cualquiera de estos métodos para alimentar los datos recopilados del cliente en una API predictiva. Los resultados se pueden integrar en la experiencia del cliente como un paso siguiente sugerido.

Los siguientes pasos intentan dar forma a los patrones de comportamiento del cliente e influyen en cómo reacciona el cliente. Dado que los pasos siguientes sugeridos se basan en algoritmos predictivos, usarán los clientes y los datos disponibles anteriores para predecir y satisfacer las necesidades del cliente, a menudo antes de que el cliente sea consciente de que la necesidad existe.