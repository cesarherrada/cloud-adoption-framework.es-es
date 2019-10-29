---
title: 'Guía de innovación de Azure: Preparación para los comentarios de los clientes'
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: Preparación para los comentarios de los clientes
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: innovate
ms.custom: fasttrack-edit, AQC
ms.localizationpriority: high
ms.openlocfilehash: ec17c66fa92abc292a19a8e74c215111d8638a05
ms.sourcegitcommit: 910efd3e686bd6b9bf93951d84253b43d4cc82b5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72769363"
---
::: zone target="docs"

# <a name="azure-innovation-guide-prepare-for-customer-feedback"></a>Guía de innovación de Azure: Preparación para los comentarios de los clientes

::: zone-end

::: zone target="chromeless"

# <a name="prepare-for-customer-feedback"></a>Preparación para los comentarios de los clientes

::: zone-end

La adopción del usuario, el compromiso y la retención son clave para la innovación correcta. ¿Por qué?

La creación de una nueva solución innovadora no consiste en ofrecer al usuario lo que desean o lo que pensamos que desean. Se trata de la formulación de una hipótesis que se pueda probar y mejorar. Las pruebas se incluyen en dos formatos: Cuantitativas (comentarios sobre la prueba), es decir, las acciones esperamos ver. Cualitativas (comentarios del cliente), que nos indican lo que significan las métricas desde el punto de vista del cliente. Juntas informan la siguiente hipótesis y la mejora siguiente a la solución. Estos bucles de comentarios son la base del [proceso de compilación-medición-aprendizaje](../considerations/adoption.md) en el núcleo de esta metodología.

Antes de integrar los bucles de comentarios, es imprescindible contar con un repositorio compartido para su solución. Un repositorio centralizado proporcionará una manera de registrar y actuar sobre todos los comentarios que se producen sobre el proyecto.  [GitHub](https://github.com/) es el hogar de software de código abierto. También es una de las plataformas que se usan con más frecuencia para hospedar el repositorio de código fuente para aplicaciones que se desarrollan comercialmente. El artículo sobre [creación de repositorios de GitHub](https://docs.microsoft.com/azure/devops/pipelines/repos/github?view=azure-devops&tabs=yaml) puede ayudarle a empezar a trabajar con su repositorio.

Cada una de las siguientes herramientas de Azure se integra con (o es compatible con) proyectos hospedados en GitHub:

## <a name="quantitative-feedback-for-web-appstabquantitative-apps"></a>[Comentarios cuantitativos para aplicaciones web](#tab/Quantitative-Apps)

Application Insights es una herramienta de supervisión que permite comentarios cuantitativos casi en tiempo real sobre el uso de su aplicación. Estos comentarios pueden ayudar a probar y validar la hipótesis actual para dar forma a la siguiente característica o caso de usuario en el trabajo pendiente.

### <a name="action"></a>.

Para ver los datos cuantitativos en las aplicaciones:

1. Vaya a **App Insights**.
2. Si su aplicación no aparece en la lista, haga clic en el vínculo **Agregar +** y siga las indicaciones para iniciar la configuración de App Insights.
3. Si la aplicación deseada está en la lista, seleccione la aplicación.
4. En el panel de **Información general** se incluyen algunas estadísticas sobre la aplicación. El vínculo **Panel de la aplicación** le permitirá crear un panel personalizado para ver los datos más relevantes para su hipótesis.

::: zone target="chromeless"

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/microsoft.insights%2Fcomponents]" submitText="Go to App Insights" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

::: zone target="docs"

Para ver los datos relacionados con sus aplicaciones, vaya al [Azure Portal](https://ms.portal.azure.com/#blade/HubsExtension/BrowseResourceBlade/resourceType/microsoft.insights%2Fcomponents).

::: zone-end

### <a name="learn-more"></a>Más información

- [Configuración de Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/learn/quick-monitor-portal)
- [Introducción a Azure Monitor App Insights](https://docs.microsoft.com/azure/azure-monitor/learn/tutorial-users)
- [Compile un panel de telemetría](https://docs.microsoft.com/azure/azure-monitor/learn/tutorial-app-dashboards)

## <a name="quantitative-feedback-for-apistabquantitative-apis"></a>[Comentarios cuantitativos para API](#tab/Quantitative-APIs)

La economía conectada está cambiando la forma en que las empresas innovan.  Los mercados y las industrias se están interrumpiendo más rápido que nunca. La interrupción tiene muchas formas y las empresas deben enfrentarse al **dilema del innovador**: cómo establecer el ritmo de cambio sin problemas en la actividad de negocio en curso.

Las empresas usan las API externamente para cambiar el modo en que interactúan con los clientes y sus asociados. Internamente, usan las API para conectar sin problemas distintas partes de la empresa. La economía de API funciona en cuatro bloques de creación: redes sociales, móviles, de análisis y de nube. Las aplicaciones y los servicios se pueden vincular de forma rápida y rentable para crear una propuesta de valor extendido.

<!-- markdownlint-disable MD024 -->

### <a name="action"></a>.

Para registrar datos cuantitativos de las API:

1. Vaya a **Servicio de API Management**.
2. Seleccione la API deseada de la lista.
3. Seleccione **Configuración de diagnóstico** en la sección **Supervisión**.

Para ver los datos cuantitativos de las API:

1. Vaya a **Servicio de API Management**.
2. Seleccione la API deseada de la lista.
3. Seleccione **Aplicación** en la sección **Supervisión**.

::: zone target="chromeless"

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.ApiManagement%2Fservice]" submitText="Go to API Management Service" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

::: zone target="docs"

Para abrir el servicio de API Management, vaya al [Azure Portal](https://ms.portal.azure.com/#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.ApiManagement%2Fservice).

::: zone-end

### <a name="learn-more"></a>Más información

Este artículo puede ayudarle a usar [Azure Monitor para obtener comentarios sobre las API](https://docs.microsoft.com/azure/api-management/api-management-howto-use-azure-monitor)

## <a name="qualitative-feedbacktabqualitative"></a>[Comentarios cualitativos](#tab/Qualitative)

El trabajo pendiente (o panel) es donde se registran los comentarios como los casos de usuario. También es donde se realiza un seguimiento del trabajo relacionado como las tareas procesables. Azure Boards se puede integrar directamente en GitHub, lo que permite una experiencia sin problemas entre la administración del trabajo de comentarios y cualquier código fuente.

::: zone target="docs"

### <a name="action"></a>.

Azure Board y Azure Pipelines requieren un portal independiente de GitHub y Azure.
Para empezar a trabajar con cualquiera de las herramientas, vaya a [Azure DevOps](https://dev.azure.com/)

::: zone-end

::: zone target="chromeless"

<!-- markdownlint-disable DOCSMD001 -->

### <a name="action"></a>.

Para crear un proyecto de DevOps:

1. Vaya a **Proyecto de Azure DevOps**.
2. Haga clic en **Crear un proyecto de DevOps**.
3. Elija **Runtime, Marco y Servicio**.

::: form action="OpenBlade[#blade/HubsExtension/BrowseResource/resourceType/microsoft.visualstudio%2Faccount%2Fproject]" submitText="Go to Azure DevOps Project" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

### <a name="learn-more"></a>Más información

Los vínculos siguientes le ayudarán a centralizar y administrar los comentarios mediante Azure Boards junto con GitHub:

- [Introducción a Azure Boards](https://docs.microsoft.com/azure/devops/boards/boards/kanban-quickstart?view=azure-devops)
- [Azure Boards y GitHub](https://docs.microsoft.com/azure/devops/boards/boards/kanban-quickstart?view=azure-devops)

## <a name="close-the-loop-with-pipelinestabpipelines"></a>[Cierre del bucle con canalizaciones](#tab/pipelines)

Actuar de acuerdo a los comentarios no siempre puede dar lugar a la característica solicitada por el cliente. Sin embargo, cada punto de datos debe producir algún cambio. Ese cambio puede estar en la forma en que piensa en las cosas. También puede ser un cambio técnico totalmente diferente del que se solicitó. En cualquier caso, las canalizaciones y herramientas de implementación como Azure Pipelines permiten publicar rápidamente esos cambios para que se puedan compartir, con frecuencia, con el cliente.

Para ver las implementaciones activas relacionadas con las aplicaciones hospedadas en Azure:

### <a name="action"></a>.

Para ver las implementaciones actuales de su canalización:

1. Vaya a **App Service**.
2. Seleccione la aplicación deseada de la lista.
3. Elija **Centro de implementación** en la sección de **Implementación** del panel de servicios de aplicaciones.

::: zone target="chromeless"

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.Web%2Fsites]" submitText="Go to App Service" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

::: zone target="docs"

Para ver las aplicaciones en App Service, vaya al [Azure Portal](https://ms.portal.azure.com/#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.Web%2Fsites).

::: zone-end

### <a name="learn-more"></a>Más información

A continuación se incluyen vínculos adicionales para empezar a crear sus canalizaciones de implementación:

- [Cree su primera canalización](https://docs.microsoft.com/azure/devops/pipelines/create-first-pipeline?view=azure-devops&tabs=tfs-2018-2)
- [Tareas de lanzamiento de GitHub](https://docs.microsoft.com/azure/devops/pipelines/tasks/utility/github-release?view=azure-devops)
