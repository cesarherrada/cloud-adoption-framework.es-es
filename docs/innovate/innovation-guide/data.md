---
title: 'Guía de innovación de Azure: Democratización de los datos'
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: Aprenda a hacer la democratización de datos con Azure.
author: absheik
ms.author: absheik
ms.date: 10/17/2019
ms.topic: conceptual
ms.service: cloud-adoption-framework
ms.subservice: innovate
ms.custom: fasttrack-new, AQC
ms.localizationpriority: high
ms.openlocfilehash: 65c1ecd1d722286fb495af3069862131629c35d1
ms.sourcegitcommit: 0d14d89b9004a65a322724342cb5086ad2c77467
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72777088"
---
::: zone target="docs"

# <a name="azure-innovation-guide-democratize-data"></a>Guía de innovación de Azure: Democratización de los datos

::: zone-end

::: zone target="chromeless"

# <a name="democratize-data"></a>Democratización de los datos

::: zone-end

Uno de los primeros pasos para realizar la democratización de datos es mejorar la detectabilidad de los datos. Catalogar y administrar los datos compartidos puede ayudar a las empresas a sacar el máximo partido de sus recursos de información existentes. Un catálogo de datos facilita que los usuarios que administran los datos puedan detectar y comprender los orígenes de los datos. Azure Data Catalog permite la administración dentro de una empresa, mientras que Azure Data Share permite la administración y el uso compartido fuera de la empresa.

Los servicios de Azure que proporcionan procesamiento de datos como Azure Time Series Insights y Stream Analytics son otras funcionalidades que los clientes y asociados están aprovechando correctamente en sus necesidades de innovación.

# <a name="catalogtabcatalog"></a>[Catálogo](#tab/Catalog)

## <a name="azure-data-catalog"></a>Azure Data Catalog

Azure Data Catalog aborda los desafíos de detección de los consumidores de datos, además de permitir a los productores de datos mantener los recursos de información. Tienda un puente entre las TI y el negocio y permita que todo el mundo aporte sus conocimientos. Deje que sus datos estén donde quiere y conéctese con las herramientas que prefiera. Controle quién puede descubrir los recursos de datos registrados. Use API de REST abiertas para integrar el servicio con las herramientas y procesos que ya utiliza.

> [!div class="checklist"]
>
> - Register
> - Buscar y anotar
> - Conecte y administre

::: zone target="docs"

**Vaya a [Azure Data Catalog](https://docs.microsoft.com/azure/data-catalog).**

::: zone-end

::: zone target="chromeless"

### <a name="action"></a>.

Solo se admite un Azure Data Catalog por organización. Si su organización ya cuenta con un catálogo, no podrá agregar más.

Para crear un Azure Data Catalog para su organización:

1. Vaya a **Azure Data Catalog**.
2. Haga clic en el botón **Crear**.

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.DataCatalog%2Fcatalogs]" submitText="Go to Azure Data Catalog" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

# <a name="sharetabshare"></a>[Compartir](#tab/Share)

## <a name="azure-data-share"></a>Azure Data Share

Lograr el equilibrio entre compartir datos abiertamente y tener control sobre los datos que se comparten y con quién es un impulsor clave de la innovación. A la vez que intentan realizar la democratización de los datos, las organizaciones pueden saturarse fácilmente por el enorme volumen, el ritmo y el ciclo de vida de dichos datos. Los proveedores de datos pueden seguir manteniendo el control de sus datos gracias a Azure Data Share. Para ello, especifican las condiciones de uso para el intercambio de datos. Quien consuma estos datos debe aceptar dichas condiciones para poder recibirlos. Los proveedores de datos pueden especificar la frecuencia con la que los consumidores de sus datos reciben actualizaciones. El proveedor de datos puede revocar el acceso a las nuevas actualizaciones en cualquier momento.

> [!div class="checklist"]
>
> - Crear una instancia de Azure Data Share.
> - Agregar conjuntos de datos a la instancia de Azure Data Share.
> - Habilitar una programación de sincronización para una instancia de Azure Data Share.
> - Agregar destinatarios a una instancia de Azure Data Share.

::: zone target="docs"
**Vaya a [Azure Data Share](https://docs.microsoft.com/azure/data-share).**

::: zone-end

::: zone target="chromeless"

<!-- markdownlint-disable MD024 -->

### <a name="action"></a>.

Para crear una instancia de Azure Data Share:

1. Vaya a **Azure Data Share**.
2. Haga clic en **Crear una instancia de Data Share**.

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.DataShare%2Faccounts]" submitText="Go to Azure Data Share" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

Use [Azure Open Datasets](https://docs.microsoft.com/azure/open-datasets/overview-what-are-open-datasets) para mejorar su análisis mediante la incorporación de datos sobre [festividades](https://azure.microsoft.com/services/open-datasets/catalog/public-holidays), [meteorológicos](https://azure.microsoft.com/services/open-datasets/catalog/noaa-global-forecast-system) y de [imágenes espaciales](https://azure.microsoft.com/services/open-datasets/catalog/hls) en sus modelos.

La información sobre la [democratización de los procesos de negocio](https://docs.microsoft.com/business-applications-release-notes/october18/microsoft-flow/democratize-business-processes) y la [capacitación de los desarrolladores de ciudadanos](https://docs.microsoft.com/business-applications-release-notes/october18/microsoft-flow/empower-citizen-developers) que se indican aquí son los pasos siguientes.

# <a name="insightstabinsights"></a>[Insights](#tab/Insights)

## <a name="azure-time-series-insights"></a>Azure Time Series Insights

Al realizar la exploración de datos casi en tiempo real de flujos de datos y el almacenamiento multicapa para los datos y los modelos de serie temporal de escala de IoT para conformar la telemetría sin procesar y derivar la información basada en recursos, las funcionalidades de innovación de datos son infinitas. Así, puede ofrecer una integración fluida y continua con otras soluciones de datos, proporcionar análisis de causas principales y detección de anomalías, incluidas las opciones de aplicación personalizadas en la plataforma de Time Series Insights.

> [!div class="checklist"]
>
> - Planee su entorno de Time Series Insights.
> - Visualización de datos en el explorador.
> - Descripción de la retención de los datos.
> - Desarrollar y compartir vistas personalizadas.

::: zone target="docs"

**Vaya a [Azure Time Series Insights](https://docs.microsoft.com/azure/time-series-insights/time-series-insights-update-overview).**

::: zone-end

::: zone target="chromeless"

<!-- markdownlint-disable DOCSMD001 -->

### <a name="action"></a>.

Para crear un entorno de Azure Time Series Insights:

1. Vaya a **Azure Time Series Insights**.
2. Haga clic en **Crear entorno de Time Series Insights**.
3. Apunte este entorno a un origen del evento, ya sea IoT Hub o un centro de eventos.

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.TimeSeriesInsights%2Fenvironments]" submitText="Go to Azure Time Series Insights" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end
