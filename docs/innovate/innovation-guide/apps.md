---
title: 'Guía de innovación de Azure: Participación mediante aplicaciones'
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: Aprenda a innovar al participar a través de aplicaciones con Azure.
author: billyclaymyersmsft
ms.author: wimyers
ms.date: 10/17/2019
ms.topic: conceptual
ms.service: cloud-adoption-framework
ms.subservice: innovate
ms.custom: fasttrack-edit, AQC
ms.localizationpriority: high
ms.openlocfilehash: df91d44d9b1efc2196b8b322c247dd39ef3d0d1e
ms.sourcegitcommit: 910efd3e686bd6b9bf93951d84253b43d4cc82b5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72769358"
---
::: zone target="docs"

# <a name="azure-innovation-guide-engage-through-apps"></a>Guía de innovación de Azure: Participación mediante aplicaciones

::: zone-end

::: zone target="chromeless"

# <a name="engage-through-apps"></a>Participación mediante aplicaciones

::: zone-end

La innovación con aplicaciones incluye la modernización de las aplicaciones existentes hospedadas en el entorno local, así como la compilación de aplicaciones nativas de la nube con contenedores o tecnologías sin servidor. En lo que respecta a la modernización de aplicaciones, Azure proporciona servicios de PaaS como Azure App Service para modernizar fácilmente las aplicaciones web y de API existentes escritas en .NET, .NET Core, Java, Node.js, Ruby, Python o PHP para su implementación en Azure. Con un modelo de contenedor de estándar abierto, la creación de microservicios o la inclusión en contenedores de sus aplicaciones actuales y su implementación en Azure es sencilla con servicios administrados como Azure Kubernetes Services, Azure Container Instances y Web App for Containers. Las tecnologías sin servidor como Azure Functions y Azure Logic Apps ayudan a centrarse en la creación de la aplicación mediante un modelo de consumo (pague por lo que use) en un lugar de implementar y administrar la infraestructura.

<!-- markdownlint-disable MD025 -->

# <a name="deliver-value-fastertabdelivervaluefaster"></a>[Entregar valor más rápido](#tab/DeliverValueFaster)

Una de las ventajas de las soluciones basadas en la nube es la capacidad de recopilar comentarios más rápido y comenzar a entregar el valor a su usuario final. Si ese usuario final es un cliente externo o un usuario de su propia compañía, cuanto más rápido pueda obtener comentarios sobre sus aplicaciones, mejor.

## <a name="azure-app-service"></a>Azure App Service

Azure App Service proporciona un entorno de hospedaje para las aplicaciones que elimina la carga de administración de la infraestructura y la aplicación de revisiones del sistema operativo. Permite la automatización del escalado para satisfacer las demandas de los usuarios, mientras está limitado por los límites que defina para mantener los costos en la comprobación.

Azure App Service ofrece compatibilidad de primera clase con lenguajes de programación como ASP.NET, ASP.NET Core, Java, Ruby, Node.js, PHP o Python. Si necesita hospedar otra pila en tiempo de ejecución, Web App for Containers le permite hospedar de forma rápida y sencilla un contenedor de Docker en el entorno de Azure App Service, con lo que se hospeda la pila de código personalizada en un entorno que permite sacar provecho de la empresa del servidor.

### <a name="action"></a>.

Para configurar o supervisar las implementaciones de Azure App Service:

1. Vaya a **App Services**.
2. Configurar un nuevo servicio: haga clic en el vínculo **Agregar +** y siga las indicaciones.
3. Administrar servicios existentes: Seleccione la aplicación que desee en la lista de aplicaciones hospedadas.

::: zone target="chromeless"

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.Web%2Fsites]" submitText="Go to App Services" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

## <a name="azure-cognitive-services"></a>Azure Cognitive Services

Azure Cognitive Services le permite incorporar la inteligencia avanzada directamente en su aplicación a través de un conjunto de API, que le permite aprovechar los algoritmos de Machine Learning y de la IA compatibles con Microsoft.

<!-- markdownlint-disable MD024 -->

### <a name="action"></a>.

Para configurar o supervisar las implementaciones de Azure Cognitive Service:

1. Vaya a **Cognitive Services**.
2. Configurar un nuevo servicio: haga clic en el vínculo **Agregar +** y siga las indicaciones.
3. Administrar servicios existentes: Seleccione el servicio que desee en la lista de servicios hospedados.

::: zone target="chromeless"

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.CognitiveServices%2Faccounts]" submitText="Go to Cognitive Services" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

## <a name="azure-bot-services"></a>Azure Bot Services

Azure Bot Services amplía su aplicación estándar para incluir una interfaz de bot natural que usa IA y Machine Learning para crear una nueva interacción para sus clientes.

### <a name="action"></a>.

Para configurar o supervisar las implementaciones de Azure Bot Services:

1. Vaya a **Servicios de Bot**.
2. Configurar un nuevo servicio: haga clic en el vínculo **Agregar +** y siga las indicaciones.
3. Administrar servicios existentes: Seleccione el bot que desee en la lista de servicios hospedados.

::: zone target="chromeless"

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.BotService%2FbotServices]" submitText="Go to Bot Services" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

## <a name="azure-devops"></a>Azure DevOps

Durante el recorrido de innovación, se encontrará con el tiempo en la ruta de acceso a DevOps. Microsoft ya ha tenido un producto local conocido como Team Foundation Server (TFS). Durante nuestro propio recorrido de innovación, Microsoft desarrolló Azure DevOps como un servicio basado en la nube que proporciona herramientas de compilación y lanzamiento que admiten muchos lenguajes y destinos diferentes para sus versiones. [Azure DevOps](https://docs.microsoft.com/azure/devops)

## <a name="visual-studio-app-center"></a>Visual Studio App Center

A medida que las aplicaciones móviles continúan creciendo en popularidad, crece la necesidad de una plataforma que pueda proporcionar pruebas automatizadas en dispositivos reales de diversas configuraciones. Visual Studio App Center no solo proporciona un lugar en el que pueda probar sus aplicaciones en iOS, Android, Windows y macOS, sino que proporciona una plataforma de supervisión con la capacidad de aprovechar Application Insights de Azure para que el motivo de la telemetría sea rápido y sencilla. Para obtener más información, consulte la [introducción a Visual Studio App Center](https://docs.microsoft.com/appcenter).

Visual Studio App Center también proporciona un servicio de notificación que permite que una sola llamada envíe notificaciones a la aplicación entre plataformas sin tener que ponerse en contacto con cada servicio de notificación de forma individual. Para obtener más información, consulte [Visual Studio App Center Push (ACP)](https://docs.microsoft.com/appcenter/push).

### <a name="read-more"></a>Más información

- [Información general de App Service](https://docs.microsoft.com/azure/app-service/overview)
- [Web Apps for Containers: Ejecutar un contenedor personalizado](https://docs.microsoft.com/azure/app-service/containers/quickstart-docker)
- [Introducción a Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-overview)
- [Azure para desarrolladores de .NET y .NET Core](https://docs.microsoft.com/dotnet/azure/?view=azure-dotnet)
- [Azure SDK para la documentación Python](https://docs.microsoft.com/azure/python)
- [Azure para desarrolladores de Java Cloud](https://docs.microsoft.com/azure/java/?view=azure-java-stable)
- [Creación de una aplicación web de PHP en Azure](https://docs.microsoft.com/azure/app-service/app-service-web-get-started-php)
- [Documentación de Azure SDK para JavaScript](https://docs.microsoft.com/azure/javascript)
- [Documentación de Azure SDK para Go](https://docs.microsoft.com/azure/go)
- [Soluciones de DevOps](https://azure.microsoft.com/solutions/devops)

# <a name="cloud-native-appstabcloudnative"></a>[Aplicaciones nativas de la nube](#tab/CloudNative)

<!-- markdownlint-disable MD026 -->

## <a name="what-are-cloud-native-applications"></a>¿Qué son las aplicaciones nativas de la nube?

Las aplicaciones nativas de la nube se crean desde cero y están optimizadas para la escala y el rendimiento de la nube. Están acoplados de forma flexible, se basan en arquitecturas de microservicios, utilizan servicios administrados, pueden ser observables y se benefician de la entrega continua para conseguir confiabilidad y una comercialización más rápida. Por lo general, son portátiles y se pueden ejecutar en entornos dinámicos como nubes públicas, privadas e híbridas. Las aplicaciones nativas de la nube se compilan normalmente con uno o varios de los siguientes enfoques:

- Microservicios
- Sin servidor
- Contenedor

## <a name="microservices"></a>Microservicios

Los microservicios son un estilo de arquitectura de software en que las aplicaciones se componen de pequeños módulos independientes que se comunican entre sí mediante contratos de API bien definidos. Estos módulos de servicios son bloques de creación altamente desacoplados, lo suficientemente pequeños para implementar una única funcionalidad. Los microservicios le ayudan a:

- Compilar servicios de forma independiente.
- Escalar servicios de forma autónoma.
- Use los enfoques más adecuados para la implementación y el lenguaje de programación.
- Aislar puntos de error.
- Entregar valor más rápido.

### <a name="azure-kubernetes-service-aks"></a>Azure Kubernetes Service (AKS)

Use un servicio de Kubernetes totalmente administrado para controlar el aprovisionamiento, la actualización y el escalado de recursos de clúster a petición. AKS facilita la implementación y administración de aplicaciones en contenedores. Ofrece Kubernetes sin servidor, una experiencia de integración y entrega continuas (CI/CD) integrada y seguridad y gobernanza de nivel empresarial. Una a sus equipos de desarrollo y de operaciones en una sola plataforma para crear, entregar y escalar aplicaciones con confianza.

#### <a name="action"></a>.

Para configurar o supervisar Azure Kubernetes Services:

1. Vaya a **Servicios de Kubernetes**.
2. Configurar un nuevo servicio: haga clic en el vínculo **Agregar +** y siga las indicaciones.
3. Administrar el servicio existente: Seleccione el servicio de Kubernetes deseado de la lista.

::: zone target="chromeless"

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResource/resourceType/Microsoft.ContainerService%2FmanagedClusters]" submitText="Go to Kubernetes Services" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

## <a name="event-based-solutions"></a>Soluciones basadas en eventos

### <a name="azure-functions"></a>Azure Functions

Azure Functions ofrece una plataforma para ejecutar pequeños fragmentos de código o funciones en la nube. Functions puede ser una manera de empezar la refactorización del código en una arquitectura de microservicios.

El tiempo de ejecución de Azure Functions admite muchos lenguajes, como C#, Java, JavaScript y Python. Para más información, consulte [Lenguajes admitidos en Azure Functions](https://docs.microsoft.com/azure/azure-functions/supported-languages).

Otra ventaja de las funciones es la posibilidad de que se desencadenen mediante acciones y eventos diferentes como HTTPTriggers, TimerTriggers y desencadenadores de otros servicios de Azure, como Blob Storage, EventGrid y ServiceBus. Para más información sobre los desencadenadores y los enlaces, consulte [Conceptos básicos sobre los enlaces y desencadenadores de Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings).

#### <a name="action"></a>.

Para configurar o supervisar las implementaciones de Azure Functions:

1. Vaya a **Aplicación de funciones**.
2. Configurar una nueva aplicación: haga clic en el vínculo **Agregar +** y siga las indicaciones.
3. Administrar las aplicaciones existentes: Seleccione la aplicación que desee de la lista de Aplicaciones de funciones.

::: zone target="chromeless"

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.Web%2Fsites/kind/functionapp]" submitText="Go to Azure Functions" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

## <a name="serverless-solutions"></a>Soluciones sin servidor

Compile aplicaciones nativas de la nube sin tener que aprovisionar ni administrar infraestructura, con una plataforma totalmente administrada en la que el escalado, la disponibilidad y el rendimiento se controlan de manera automática. Entre las ventajas de las soluciones sin servidor de Azure se incluyen:

- Aumento de la velocidad del desarrollador
- Impulso del rendimiento del equipo
- Aumento del impacto de su organización

### <a name="azure-logic-apps"></a>Azure Logic Apps

Integre datos y aplicaciones en lugar de escribir complejo código de adherencia entre sistemas dispares. Cree flujos de trabajo sin servidor de manera visual con Azure Logic Apps y use sus propias API, funciones sin servidor o conectores de software como servicio (SaaS) listos para usar, incluidos Salesforce, Microsoft Office 365 y Dropbox.

#### <a name="action"></a>.

Para configurar o supervisar Azure Logic Apps:

1. Vaya a **Logic Apps**.
2. Configurar una nueva aplicación: haga clic en el vínculo **Agregar +** y siga las indicaciones.
3. Administrar las aplicaciones existentes: Seleccione de la lista la aplicación lógica que desee.

::: zone target="chromeless"

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.Logic%2Fworkflows]" submitText="Go to Azure Logic Apps" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

### <a name="serverless-api-management"></a>Administración de API sin servidor

Publique, proteja, transforme, mantenga y supervise API con Azure API Management, un servicio totalmente administrado que ofrece un modelo de uso diseñado e implementado para ser parte integral de las aplicaciones sin servidor.

#### <a name="action"></a>.

Para configurar o supervisar servicios de API Management:

1. Vaya a **Servicios de API Management**.
2. Configurar un nuevo servicio: haga clic en el vínculo **Agregar +** y siga las indicaciones.
3. Administrar el servicio existente: Seleccione el servicio deseado de la lista.

::: zone target="chromeless"

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.ApiManagement%2Fservice]" submitText="Go to API Management Services" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

## <a name="containers"></a>Contenedores

Cuando se trata de modernizar la cartera de aplicaciones, Azure proporciona diversos servicios de contenedor para levantar y mover las aplicaciones existentes a los contenedores, así como crear aplicaciones de microservicios nativas de la nube para ofrecer valor a los usuarios con más rapidez. Utilice un desarrollador de un extremo a otro y herramientas de CI/CD para desarrollar, actualizar e implementar sus aplicaciones de contenedor. Administre contenedores a escala con un servicio de orquestación de contenedores Kubernetes totalmente administrado que se integra con Azure Active Directory. Dondequiera que se encuentre en el proceso de modernización de aplicaciones, acelere el desarrollo de aplicaciones en contenedor y cumpla los requisitos de seguridad.

### <a name="azure-container-instances"></a>Azure Container Instances

Ejecute contenedores de Docker a petición en un entorno de Azure administrado y sin servidor. Azure Container Instances (ACI) es una solución para cualquier escenario que puede funcionar en contenedores aislados, sin orquestación. Si ejecuta las cargas de trabajo en ACI, puede dedicarse al diseño y la creación de aplicaciones y no a la administración de la infraestructura en la que se ejecutan.

### <a name="action"></a>.

Para configurar o supervisar instancias de contenedor:

1. Vaya a **instancia de contenedor**.
2. Configurar una nueva instancia de contenedor: haga clic en el vínculo **Agregar +** y siga las indicaciones.
3. Administrar instancia de contenedor existentes: Seleccione la instancia de contenedor que desee en la lista.

::: zone target="chromeless"

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/Microsoft.ContainerInstance%2FcontainerGroups]" submitText="Go to Container instances" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

### <a name="azure-red-hat-openshift"></a>Red Hat OpenShift en Azure

Red Hat OpenShift en Azure proporciona una implementación de autoservicio flexible de los clústeres de OpenShift totalmente administrados. Mantenga el cumplimiento normativo y dedíquese al desarrollo de aplicaciones mientras Microsoft y Red Hat se ocupan de actualizar y supervisar los nodos maestros, de infraestructura y de aplicación, así como de aplicarles las revisiones necesarias. Elija sus propias soluciones de almacenamiento, red, registro o de CI/CD o bien comenzar a usar rápidamente las soluciones integradas con administración de código fuente automatizada, la creación de contenedores y aplicaciones, implementaciones, el escalado, la administración del estado, etc.

**Vaya a [Red Hat OpenShift en Azure](https://docs.microsoft.com/azure/openshift/intro-openshift)**

# <a name="isolate-points-of-failuretabisolatepointsoffailure"></a>[Aislar puntos de error](#tab/IsolatePointsOfFailure)

Cuando empiece a realizar la transición desde la fase de pruebas inicial, evalúe las maneras de aislar y quitar puntos de error. Debido a la naturaleza distribuida de la nube de Azure, puede diseñar su aplicación para minimizar los errores y mejorar también el rendimiento.

## <a name="azure-front-door"></a>Azure Front Door

Azure Front Door proporciona un punto de entrada seguro y escalable para ofrecer su aplicación en todo el mundo. Azure Front Door combina la optimización del tráfico para lograr un mejor rendimiento y una conmutación por error global instantánea. Si necesita la finalización con el protocolo de seguridad de la capa de transporte (TLS) (descarga SSL) o el procesamiento de capas de aplicación por solicitud HTTP/HTTPS, se le debe dar preferencia a Azure Front Door en vez de a Traffic Manager.

### <a name="action"></a>.

Para configurar o supervisar las puertas delanteras:

1. Vaya a **Front Doors**.
2. Configurar una nueva puerta delantera: haga clic en el vínculo **Agregar +** y siga las indicaciones.
3. Administrar las puertas delanteras existentes: Seleccione la puerta delantera deseada de la lista.

::: zone target="chromeless"

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResource/resourceType/Microsoft.Network%2Ffrontdoors]" submitText="Go to Front Doors" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

## <a name="traffic-manager"></a>Traffic Manager

Traffic Manager proporciona equilibrio de carga basado en DNS que se puede enrutar en función de diferentes reglas. Esto ayuda a garantizar la resistencia si se produce un error en cualquier servicio implementado. También puede apilar Traffic Manager para usar el enrutamiento basado en errores y el enrutamiento basado en el rendimiento, lo que proporciona la mejor experiencia posible en función de la geografía.

### <a name="action"></a>.

Para configurar o supervisar perfiles de Traffic Manager:

1. Vaya a **Perfiles de Traffic Manager**.
2. Configurar un nuevo perfil: haga clic en el vínculo **Agregar +** y siga las indicaciones.
3. Administrar perfiles existentes: Seleccione el perfil deseado de la lista.

::: zone target="chromeless"

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResource/resourceType/Microsoft.Network%2Ftrafficmanagerprofiles]" submitText="Go to Traffic Manager profiles" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

## <a name="azure-content-delivery-network"></a>Azure Content Delivery Network

Azure ofrece una red de entrega de contenido (CDN) distribuida que permite garantizar la entrega puntual de los recursos, mediante el almacenamiento en caché cerca de los usuarios finales. Este almacenamiento en caché ayuda a mejorar la experiencia de sus clientes y evita problemas al descargar contenido causados por problemas de red entre el punto de conexión de CDN y el centro de datos que hospeda la aplicación. Esta red CDN también la pueden usar aplicaciones no hospedadas en Azure.

### <a name="action"></a>.

Para configurar o supervisar los perfiles de red CDN:

1. Vaya a **Perfiles de red CDN**.
2. Configurar un nuevo perfil: haga clic en el vínculo **Agregar +** y siga las indicaciones.
3. Administrar perfiles existentes: Seleccione el perfil deseado de la lista.

::: zone target="chromeless"

<!-- markdownlint-disable DOCSMD001 -->

::: form action="OpenBlade[#blade/HubsExtension/BrowseResourceBlade/resourceType/microsoft.cdn%2Fprofiles]" submitText="Go to CDN profiles" :::

<!-- markdownlint-enable DOCSMD001 -->

::: zone-end

### <a name="read-more"></a>Más información

- [Azure Front Door](https://docs.microsoft.com/azure/frontdoor/front-door-overview)
- [Traffic Manager](https://docs.microsoft.com/azure/traffic-manager)
- [Content Delivery Network](https://docs.microsoft.com/azure/cdn)
