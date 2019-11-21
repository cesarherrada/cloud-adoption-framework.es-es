---
title: 'Guía de innovación de Azure: Interacción a través de dispositivos'
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: 'Guía de innovación de Azure: interacción a través de dispositivos'
author: umarmohamedusman
ms.author: umarm
ms.date: 10/10/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: innovate
ms.custom: fasttrack-new, AQC
ms.localizationpriority: high
ms.openlocfilehash: cf0671d4ea4c8d008010d43379cd782ff58e38ed
ms.sourcegitcommit: 3655aa7f3e80249e0b2b562cd40dd750afc82043
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2019
ms.locfileid: "74251881"
---
::: zone target="docs"

# <a name="azure-innovation-guide-interact-through-devices"></a>Guía de innovación de Azure: Interacción a través de dispositivos

::: zone-end

::: zone target="chromeless"

# <a name="interact-through-devices"></a>Interacción a través de dispositivos

::: zone-end

Innovación a través de dispositivos perimetrales perceptivos y conectados intermitentemente. Organice millones de estos dispositivos, adquiera y procese datos sin límites y aproveche las ventajas de un número cada vez mayor de experiencias multidispositivos y multisentidos. En el caso de los dispositivos en el borde de la red, Azure proporciona un marco para crear soluciones empresariales envolventes y eficaces. Con la informática omnipresente, hecha realidad gracias a Azure en conjunto con la tecnología de inteligencia artificial (IA), puede compilar todos los tipos de aplicación y sistema inteligentes que pueda idear.

Los clientes de Azure emplean un conjunto de sistemas y dispositivos conectados en constante expansión que recaba y analiza datos&mdash;cerca de los usuarios, de los datos o de ambos. Los usuarios obtienen conclusiones y experiencias en tiempo real, a través de aplicaciones con gran capacidad de respuesta y conscientes del contexto. Al mover elementos de la carga de trabajo al borde, estos dispositivos pueden dedicar menos tiempo a enviar mensajes a la nube y reaccionar más rápidamente a los eventos espaciales.

> [!div class="checklist"]
>
> - Recursos industriales
> - HoloLens 2
> - Azure Sphere
> - Kinect DK
> - Drones
> - Azure SQL Database Edge
> - IoT Plug and Play

<!-- markdownlint-disable MD025 -->

## <a name="global-scale-iot-servicetabiothub"></a>[Servicio de IoT a escala global](#tab/IoTHub)

<!-- markdownlint-enable MD025 -->

Diseñe soluciones que ejerzan comunicación bidireccional con dispositivos de IoT a escala de miles de millones. Utilice datos de telemetría enviados desde el dispositivo a la nube listos para usar para determinar el estado de sus dispositivos y definir rutas de mensajes hacia otros servicios de Azure solo con la configuración. Al aprovechar los mensajes enviados de la nube al dispositivo, puede enviar comandos y notificaciones de forma confiable a los dispositivos conectados y realizar un seguimiento de la entrega de los mensajes con acuses de recibo. Los mensajes de los dispositivos se reenviarán automáticamente según sea necesario para ajustarse a una conectividad intermitente.

Estas son algunas de las características que encontrará:

- Canal de **comunicación con seguridad mejorada** para enviar y recibir datos desde los dispositivos de IoT.
- **Administración de dispositivos integrada** y aprovisionamiento para conectarse y administrar dispositivos IoT a escala.
- **Integración total con Event Grid** y la informática sin servidor, para simplificar el desarrollo de aplicaciones de IoT.
- **Compatibilidad con Azure IoT Edge** para crear aplicaciones de IoT híbridas.

::: zone target="docs"

**Vaya a [IoT Hub](https://docs.microsoft.com/azure/iot-dps)**

**Vaya a [Servicios de aprovisionamiento de dispositivos](https://docs.microsoft.com/azure/iot-dps)**

::: zone-end

::: zone target="chromeless"

### <a name="action"></a>.

Para crear un centro de IoT:

1. Vaya a **IoT Hub**.
2. Seleccione **Crear IoT Hub**.

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResource/resourceType/Microsoft.Devices%2FIotHubs]" submitText="Go to IoT Hub" :::

<!-- markdownlint-enable DOCSMD001 -->

El IoT Hub Device Provisioning es un servicio auxiliar de IoT Hub que permite un aprovisionamiento sin interacción cuando es necesario.

<!-- markdownlint-disable MD024 -->

### <a name="action"></a>.

Para crear servicios de IoT Hub Device Provisioning Service:

1. Vaya a **IoT Hub Device Provisioning Services**.
2. Seleccione **Crear servicios de aprovisionamiento de dispositivos**.

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResource/resourceType/Microsoft.Devices%2FProvisioningServices]" submitText="Go to Device Provisioning Services" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

<!-- markdownlint-disable MD025 -->

## <a name="azure-digital-twinstabdigitaltwins"></a>[Azure Digital Twins](#tab/DigitalTwins)

Cree experiencias reutilizables, muy escalables y con reconocimiento del espacio que vinculan la transmisión de los datos entre el mundo físico y el digital. Mejore la interacción con su cliente mediante modelos completos de entornos físicos. Cree grafos de inteligencia espacial para modelar las relaciones y las interacciones entre personas, lugares y dispositivos. Consulte datos de un espacio físico y no a partir de sensores diferentes.

**Modelos de objetos de Azure Digital Twins:** Una ontología que describe las regiones, los lugares, las plantas, las oficinas, las zonas, las salas de conferencias y los salones de foco de una construcción inteligente, o varias estaciones de alimentación, subestaciones, recursos energéticos y clientes de una red de energía, se puede modelar mediante ontologías y modelos de objetos de Digital Twins.

**Grafo de inteligencia espacial:** Grafo jerárquico de espacios, dispositivos y personas definidos en el modelo de objetos de Digital Twins que admite la herencia, el filtrado, el recorrido, la escalabilidad y la extensibilidad. Puede administrar el grafo espacial e interactuar con él mediante la colección de API REST hospedada en Azure.

::: zone target="docs"

**Vaya a [Azure Digital Twins](https://docs.microsoft.com/azure/digital-twins/about-digital-twins)**

::: zone-end

::: zone target="chromeless"

### <a name="action"></a>.

Para crear Azure Digital Twins:

1. En el panel izquierdo, seleccione **Crear un recurso**.
2. Busque **digital twins** y después seleccione **Digital Twins**.
3. Haga clic en **Crear** para iniciar el proceso de implementación.
4. Para revisar las instancias existentes de Digital Twins, seleccione este botón:

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResource/resourceType/Microsoft.IoTSpaces%2FGraph]" submitText="Go to Digital Twins" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

<!-- markdownlint-disable MD025 -->

## <a name="location-intelligencetabazuremaps"></a>[Inteligencia de ubicación](#tab/AzureMaps)

Además de las funcionalidades de ubicación tradicionales, tales como proximidad, tráfico y enrutamiento, el servicio de Azure Maps permite a las empresas crear soluciones mediante inteligencia de ubicación en tiempo real que funciona con tecnología de movilidad de clase mundial de los asociados **TomTom** y **Moovit**. Integre fácilmente características de movilidad y ubicación avanzadas en sus aplicaciones con servicios geoespaciales.

**Versión preliminar de Data Service:** Cargue y almacene datos geoespaciales para usar con operaciones espaciales o composición de imágenes para reducir la latencia, aumentar la productividad y habilitar nuevos escenarios en sus aplicaciones.

**Operaciones espaciales:** Mejore su inteligencia de ubicación con una biblioteca de cálculos matemáticos geoespaciales comunes, como geovalla, punto más cercano, distancia ortodrómica y límites de ruta.

**Geolocalización:** Busque el país de una dirección IP. Personalice el contenido y los servicios de acuerdo con la ubicación del usuario y obtenga conclusiones sobre la distribución geográfica de los clientes.

::: zone target="docs"

**Vaya a [Azure Maps](https://docs.microsoft.com/azure/azure-maps)**

::: zone-end

::: zone target="chromeless"

### <a name="action"></a>.

Para usar la inteligencia de ubicación:

1. Vaya a **Cuentas de Azure Maps**.
2. Seleccione **Crear cuentas de Azure Maps**.

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.Maps%2Faccounts]" submitText="Go to Azure Maps Account" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

## <a name="spatial-experiencestabspatial"></a>[Experiencias espaciales](#tab/spatial)

Azure Spatial Anchors permite a los desarrolladores trabajar con plataformas de realidad mixta para percibir el espacio, designar puntos precisos de interés y volver a recuperar esos puntos de interés desde los dispositivos compatibles.

**Agregue contexto al mundo real:** Ofrezca a sus usuarios un mejor reconocimiento de sus datos, donde y cuando lo necesiten, colocando y conectando a puntos de interés físicos su contenido digital.

**Comparta hologramas entre dispositivos:** Agilice la toma de decisiones y la obtención de resultados ofreciendo visualización 3D a su equipo y a sus clientes en el dispositivo que prefieran. Spatial Anchors permite a personas que están en el mismo lugar participar en aplicaciones de realidad mixta multiusuario.

**Experiencias atractivas:** Conecte los anclajes espaciales mediante la creación de relaciones entre ellos y proporcione una experiencia de usuario que puede incluir dos o más puntos de interés con los que un usuario debe interactuar para completar una tarea. La aplicación puede permitir que un usuario coloque un artefacto virtual en el mundo real. En un entorno industrial, un usuario podría recibir información contextual sobre una máquina señalándola con la cámara de un dispositivo compatible.

Azure Spatial Anchors está compuesto por un servicio administrado y el SDK de cliente para las plataformas de dispositivos compatibles.

::: zone target="docs"

**Vaya a [Azure Spatial Anchors](https://azure.microsoft.com/services/spatial-anchors)**

::: zone-end

::: zone target="chromeless"

### <a name="action"></a>.

Para usar las experiencias espaciales:

1. Vaya a **Cuentas de Spatial Anchors**.
2. Seleccione **Crear cuentas de Spatial Anchors**.

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResource/resourceType/Microsoft.MixedReality%2FspatialAnchorsAccounts]" submitText="Go to Spatial Anchors Accounts" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

## <a name="azure-remote-renderingtabremoterender"></a>[Azure Remote Rendering](#tab/RemoteRender)

Represente contenido 3D interactivo de alta calidad en la nube y transmítalo mediante streaming a sus dispositivos en tiempo real. Las cargas de trabajo de representación se usa mucho para efectos especiales (VFX) en el sector multimedia y de entretenimiento. La representación también se usa en muchos otros sectores, como la publicidad, el mercado minorista, petróleo y gas y fabricación.

El proceso de representación es intensivo computacionalmente. Puede haber muchos fotogramas o imágenes para generar y cada imagen puede tardar varias horas en representarse. Por lo tanto, la representación es una carga de trabajo de procesamiento por lotes perfecta que puede aprovechar Azure y Azure Batch para ejecutar muchas representaciones en paralelo.

::: zone target="docs"

**Vaya a [Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering)**

**Vaya a [Representación mediante Azure](https://docs.microsoft.com/azure/batch/batch-rendering-service)**

::: zone-end

::: zone target="chromeless"

### <a name="action"></a>.

Para usar Remote Rendering:

1. Vaya a **Cuentas de Batch**.
2. Seleccione **Crear cuentas de Batch**.

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.Batch%2FbatchAccounts]" submitText="Go to Azure Batch" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end
