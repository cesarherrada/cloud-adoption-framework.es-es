---
title: 'Innovación de Azure: Preparación de comentarios'
description: Aprenda a usar herramientas de Azure para recopilar comentarios cuantitativos y cualitativos sobre aplicaciones web y API hospedadas en GitHub.
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: innovate
ms.custom: fasttrack-edit, AQC
ms.localizationpriority: high
ms.openlocfilehash: 95087aeda19eb87759bc09f605c42c706d79aac2
ms.sourcegitcommit: 58ea417a7df3318e3d1a76d3807cc4e7e3976f52
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2020
ms.locfileid: "78891960"
---
::: zone target="docs"

# <a name="azure-innovation-guide-prepare-for-customer-feedback"></a>Guía de innovación de Azure: Preparación para los comentarios de los clientes

::: zone-end

::: zone target="chromeless"

# <a name="prepare-for-customer-feedback"></a>Preparación para los comentarios de los clientes

::: zone-end

La adopción del usuario, el compromiso y la retención son clave para la innovación correcta. ¿Por qué?

La creación de una nueva solución innovadora no consiste en ofrecer a los usuarios lo que desean o lo que pensamos que desean. Se trata de la formulación de una hipótesis que se pueda probar y mejorar. Las pruebas se incluyen en dos formatos:

- **Cuantitativas (comentarios sobre la prueba):** estos comentarios miden las acciones que esperamos ver.
- **Cualitativas (comentarios del cliente):** estos comentarios nos indican lo que significan las métricas desde el punto de vista del cliente.

Antes de integrar bucles de comentarios, debe tener un repositorio compartido para la solución. Un repositorio centralizado proporcionará una manera de registrar todos los comentarios que se emiten sobre el proyecto, así como actuar sobre estos. [GitHub](https://github.com) es el hogar de software de código abierto. También es una de las plataformas que se usan con más frecuencia para hospedar los repositorios de código fuente para aplicaciones que se desarrollan comercialmente. El artículo sobre [creación de repositorios de GitHub](https://docs.microsoft.com/azure/devops/pipelines/repos/github?view=azure-devops&tabs=yaml) puede ayudarle a empezar a trabajar con su repositorio.

Cada una de las siguientes herramientas de Azure se integra (o es compatible) con proyectos hospedados en GitHub:

## <a name="quantitative-feedback-for-web-apps"></a>[Comentarios cuantitativos para aplicaciones web](#tab/Quantitative-Apps)

Application Insights es una herramienta de supervisión que proporciona comentarios cuantitativos casi en tiempo real sobre el uso de su aplicación. Estos comentarios pueden ayudarle a probar y validar la hipótesis actual para dar forma a la siguiente característica o caso de usuario en el trabajo pendiente.

### <a name="action"></a>Acción

Para ver los datos cuantitativos en las aplicaciones:

1. Vaya a **Application Insights**.
   - Si su aplicación no aparece en la lista, seleccione **Agregar** y siga las indicaciones para iniciar la configuración de Application Insights.
   - Si la aplicación deseada está en la lista, selecciónela.
1. En el panel de **Información general** se incluyen algunas estadísticas sobre la aplicación. Seleccione **Panel de la aplicación** para crear un panel personalizado con los datos más relevantes para su hipótesis.

::: zone target="chromeless"

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/microsoft.insights%2Fcomponents]" submitText="Go to Application Insights" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

::: zone target="docs"

Para ver los datos sobre sus aplicaciones, vaya a [Azure Portal](https://ms.portal.azure.com/#blade/HubsExtension/BrowseResourceBlade/resourceType/microsoft.insights%2Fcomponents).

::: zone-end

### <a name="learn-more"></a>Más información

- [Configuración de Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/learn/quick-monitor-portal)
- [Introducción a Azure Monitor Application Insights](https://docs.microsoft.com/azure/azure-monitor/learn/tutorial-users)
- [Compile un panel de telemetría](https://docs.microsoft.com/azure/azure-monitor/learn/tutorial-app-dashboards)

## <a name="quantitative-feedback-for-apis"></a>[Comentarios cuantitativos para API](#tab/Quantitative-APIs)

La economía conectada está cambiando la forma en que las empresas innovan. Los mercados y las industrias se están interrumpiendo más rápido que nunca. La interrupción tiene muchas formas y las empresas deben enfrentarse al _dilema del innovador_: cómo establecer el ritmo de cambio sin chocar con la actividad de negocio en curso.

Las empresas usan las API externamente para cambiar el modo en que interactúan con sus clientes y asociados. Internamente, usan las API para conectar sin problemas distintas partes de la empresa. La economía de API funciona en cuatro bloques de creación: redes sociales, móviles, análisis y nube. Las aplicaciones y los servicios se pueden vincular de forma rápida y rentable para crear una propuesta de valor extendido.

<!-- markdownlint-disable MD024 -->

### <a name="action"></a>Acción

Para registrar datos cuantitativos de las API:

1. Vaya a **Servicios de API Management**.
2. Seleccione la API deseada de la lista.
3. Seleccione **Configuración de diagnóstico** en la sección **Supervisión**.

Para ver los datos cuantitativos de las API:

1. Vaya a **Servicios de API Management**.
2. Seleccione la API deseada de la lista.
3. Seleccione **Aplicación** en la sección **Supervisión**.

::: zone target="chromeless"

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.ApiManagement%2Fservice]" submitText="Go to API Management services" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

::: zone target="docs"

Para abrir los servicios de API Management, vaya a [Azure Portal](https://ms.portal.azure.com/#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.ApiManagement%2Fservice).

::: zone-end

### <a name="learn-more"></a>Más información

- [Uso de Azure Monitor para obtener comentarios sobre las API](https://docs.microsoft.com/azure/api-management/api-management-howto-use-azure-monitor)

## <a name="qualitative-feedback"></a>[Comentarios cualitativos](#tab/Qualitative)

El trabajo pendiente (o panel) es donde se registran los comentarios como los casos de usuario. También es donde se realiza un seguimiento del trabajo relacionado como tareas procesables. Azure Boards se puede integrar directamente en GitHub, lo que permite una experiencia sin problemas entre la administración del trabajo de comentarios y cualquier código fuente.

::: zone target="docs"

### <a name="action"></a>Acción

Azure Board y Azure Pipelines requieren un portal independiente de GitHub y Azure. Introducción al uso de [Azure DevOps](https://dev.azure.com).

::: zone-end

::: zone target="chromeless"

<!-- markdownlint-disable DOCSMD001 -->

### <a name="action"></a>Acción

Para crear un proyecto de DevOps:

1. Vaya a **Azure DevOps Projects**.
2. Seleccione **Crear un proyecto de DevOps**.
3. Seleccione **Runtime, Marco y Servicio**.

::: form action="OpenBlade[#blade/HubsExtension/BrowseResource/resourceType/microsoft.visualstudio%2Faccount%2Fproject]" submitText="Go to Azure DevOps Projects" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

### <a name="learn-more"></a>Más información

Estos artículos le ayudarán a centralizar y administrar los comentarios utilizando Azure Boards junto con GitHub:

- [Introducción a Azure Boards](https://docs.microsoft.com/azure/devops/boards/get-started/?view=azure-devops)
- [Azure Boards y GitHub](https://docs.microsoft.com/azure/devops/boards/github?view=azure-devops)

## <a name="close-the-loop-with-pipelines"></a>[Cierre del bucle con canalizaciones](#tab/pipelines)

Actuar de acuerdo a los comentarios no siempre significa agregar la característica que solicita el cliente. Sin embargo, cada punto de datos debe producir algún cambio. Ese cambio puede estar en su manera de pensar en las cosas. También puede ser un cambio técnico totalmente diferente del solicitado. En cualquier caso, las canalizaciones y herramientas de implementación como Azure Pipelines permiten publicar rápidamente esos cambios para que se puedan compartir con el cliente con frecuencia.

### <a name="action"></a>Acción

Para ver las implementaciones actuales de su canalización:

1. Vaya a **App Services**.
2. Seleccione la aplicación deseada de la lista.
3. Seleccione **Centro de implementación** en la sección **Implementación** del panel de App Services.

::: zone target="chromeless"

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.Web%2Fsites]" submitText="Go to App Services" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

::: zone target="docs"

Para ver las aplicaciones en App Service, vaya al [Azure Portal](https://ms.portal.azure.com/#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.Web%2Fsites).

::: zone-end

### <a name="learn-more"></a>Más información

Comience a crear sus canalizaciones de implementación:

- [Cree su primera canalización](https://docs.microsoft.com/azure/devops/pipelines/create-first-pipeline?view=azure-devops&tabs=tfs-2018-2)
- [Tareas de lanzamiento de GitHub](https://docs.microsoft.com/azure/devops/pipelines/tasks/utility/github-release?view=azure-devops)
