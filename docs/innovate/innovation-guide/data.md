---
title: 'Innovación de Azure: Democratización de los datos'
description: Más información sobre Azure Data Catalog, Azure Data Share y otras herramientas que mejoran la detección y comprensión de los datos.
author: absheik
ms.author: absheik
ms.date: 10/17/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: innovate
ms.custom: fasttrack-new, AQC
ms.localizationpriority: high
ms.openlocfilehash: 6981af0cab1d9be149675a85f09be0640970e30f
ms.sourcegitcommit: 388e32dd4861039149c846c926c0e9230cf28ae3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79140174"
---
<!-- cSpell:ignore Fcatalogs Faccounts FEnvironments -->

::: zone target="docs"

# <a name="azure-innovation-guide-democratize-data"></a>Guía de innovación de Azure: Democratización de los datos

::: zone-end

::: zone target="chromeless"

# <a name="democratize-data"></a>Democratización de los datos

::: zone-end

Uno de los primeros pasos para la democratización de datos es mejorar la detectabilidad de los datos. Catalogar y administrar los datos compartidos puede ayudar a las empresas a sacar el máximo partido de sus recursos de información existentes. Un catálogo de datos facilita que los usuarios que administran los datos puedan detectar y comprender los orígenes de datos. Azure Data Catalog permite la administración dentro de una empresa, mientras que Azure Data Share permite la administración y el uso compartido fuera de la empresa.

Los servicios de Azure que proporcionan procesamiento de datos como Azure Time Series Insights y Stream Analytics son otras funcionalidades que los clientes y asociados usan correctamente en sus necesidades de innovación.

# <a name="catalog"></a>[Catálogo](#tab/Catalog)

## <a name="azure-data-catalog"></a>Azure Data Catalog

Azure Data Catalog aborda los desafíos de detección de los consumidores de datos, además de permitir a los productores de datos mantener los recursos de información. Tiende un puente entre el personal de TI y la empresa, y permite que todo el mundo aporte sus conocimientos. Puede almacenar los datos donde quiera y conectarse con las herramientas que prefiera usar. Con Azure Data Catalog, puede controlar quién puede detectar los recursos de datos registrados. Use las API de REST abiertas para integrar el servicio con las herramientas y los procesos que ya utiliza.

> [!div class="checklist"]
>
> - Register
> - Buscar y anotar
> - Conectar y administrar

::: zone target="docs"

**Consulte la [documentación de Azure Data Catalog](https://docs.microsoft.com/azure/data-catalog)**

::: zone-end

::: zone target="chromeless"

### <a name="action"></a>Acción

Solo se admite una instancia de Azure Data Catalog por organización. Si su organización ya cuenta con una instancia de Data Catalog, no podrá agregar más catálogos.

Para crear una instancia de Azure Data Catalog para su organización:

1. Vaya a **Azure Data Catalog**.
2. Seleccione **Crear**.

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.DataCatalog%2Fcatalogs]" submitText="Go to Azure Data Catalog" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

# <a name="share"></a>[Compartir](#tab/Share)

## <a name="azure-data-share"></a>Azure Data Share

Lograr el equilibrio entre compartir datos abiertamente y ejercer control sobre los datos que se comparten y con quién es un impulsor clave de la innovación. Al intentar realizar la democratización de los datos, las organizaciones pueden saturarse fácilmente por el enorme volumen, el ritmo y el ciclo de vida de dichos datos. Azure Data Share garantiza que los proveedores puedan controlar cómo se gestionan sus datos. Para ello, deben especificar las condiciones de uso del recurso compartido de datos. Quien consuma estos datos debe aceptar esas condiciones para poder recibirlos. Los proveedores de datos pueden especificar la frecuencia con la que los consumidores de sus datos reciben actualizaciones. El proveedor de datos puede revocar el acceso a las nuevas actualizaciones en cualquier momento.

> [!div class="checklist"]
>
> - Crear una instancia de Azure Data Share.
> - Agregar conjuntos de datos a la instancia de Azure Data Share.
> - Habilitar una programación de sincronización para una instancia de Azure Data Share.
> - Agregar destinatarios a una instancia de Azure Data Share.

::: zone target="docs"
**Consulte la [documentación de Azure Data Share](https://docs.microsoft.com/azure/data-share)**

::: zone-end

::: zone target="chromeless"

<!-- markdownlint-disable MD024 -->

### <a name="action"></a>Acción

Para crear un recurso compartido de datos:

1. Vaya a **Azure Data Shares** (Instancias de Azure Data Share).
2. Seleccione **Create data share** (Crear una instancia de Data Share).

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.DataShare%2Faccounts]" submitText="Go to Azure Data Shares" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

# <a name="insights"></a>[Insights](#tab/Insights)

## <a name="azure-time-series-insights"></a>Azure Time Series Insights

Las capacidades de innovación de datos de Azure Time Series Insights son interminables. Proporciona exploración de datos casi en tiempo real de flujos de datos y almacenamiento multicapa para los datos de series temporales de escala de IoT. También proporciona modelos para contextualizar datos de telemetría sin procesar y derivar información basada en recursos. Así, puede ofrecer una integración fluida y continua con otras soluciones de datos, así como proporcionar análisis de causas principales y detección de anomalías, incluidas las opciones de aplicación personalizadas en la plataforma de Time Series Insights.

> [!div class="checklist"]
>
> - Planee su entorno de Time Series Insights.
> - Visualización de datos en el explorador.
> - Descripción de la retención de los datos.
> - Desarrollar y compartir vistas personalizadas.

::: zone target="docs"

**Consulte el tema de [introducción a Azure Time Series Insights](https://docs.microsoft.com/azure/time-series-insights/time-series-insights-update-overview)**

::: zone-end

::: zone target="chromeless"

### <a name="action"></a>Acción

Para crear un entorno de Azure Time Series Insights:

1. Consulte el tema sobre los **entornos de Azure Time Series Insights**.
2. Seleccione **Crear entorno de Time Series Insights**.
3. Apunte este entorno a un origen del evento, ya sea Azure IoT Hub o Event Hubs.

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.TimeSeriesInsights%2Fenvironments]" submitText="Go to Azure Time Series Insights" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end
