---
title: 'Innovación en la nube: Participación mediante aplicaciones'
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: 'Introducción a la innovación en la nube: participación mediante aplicaciones'
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: innovate
ms.openlocfilehash: 3db2349e3c1da7c80f3089ea187a3de72d006d1f
ms.sourcegitcommit: f3371811a36e12533ecbc3aa936e2a68e0cee25f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2019
ms.locfileid: "72683284"
---
# <a name="engage-through-applications"></a>Participación mediante aplicaciones

Tal y como se describe en el artículo sobre la [democratización de los datos](./data.md), estos son el nuevo petróleo. Alimentan la mayoría de las innovaciones en la economía digital. Según esta analogía, las aplicaciones serían la estación de servicio y la infraestructura necesaria para que dicho combustible se encuentre en las manos adecuadas.

En algunos casos, los datos son suficiente para producir un cambio y satisfacer las necesidades de los clientes. Lo más frecuente es que la solución para las necesidades de los clientes requiera aplicaciones para dar forma a los datos y crear una experiencia. Las aplicaciones son la manera de interactuar con el usuario. Son el inicio de los procesos necesarios para responder a los desencadenantes de los clientes. Son los medios que tienen los clientes para proporcionar datos y recibir instrucciones. En este artículo se describen algunos principios que ayudarán a alinear la solución de aplicación correcta, en función de la hipótesis que se vaya a validar.

![Participación mediante aplicaciones](../../_images/innovate/engage-via-apps.png)

## <a name="shared-code"></a>Código compartido

El equipo que pueda responder con mayor rapidez y precisión a los comentarios de los clientes, los cambios en el mercado y las oportunidades de innovación, liderará sus respectivos mercados en la innovación. El primer principio de las aplicaciones innovadoras se describe en la [información general sobre la mentalidad de crecimiento](./learn.md#growth-mindset), "Compartir el código". La innovación a lo largo del tiempo, solo puede proceder de un enfoque cultural. Para sostener la innovación, se necesitarán diferentes perspectivas y contribuciones.

Para estar preparado para la innovación, todo el desarrollo de aplicaciones debe comenzar por un repositorio de código compartido. La herramienta más común para administrar los repositorios de código es [GitHub](https://guides.github.com/), que permite la creación de un repositorio de código compartido con unos pocos clics. Como alternativa, se puede usar la característica [Azure Repos](/azure/devops/repos/get-started/what-is-repos?view=azure-devops) de Azure DevOps para crear un [Git](/azure/devops/repos/get-started/what-is-repos?view=azure-devops#git) o repositorio de [Team Foundation](/azure/devops/repos/get-started/what-is-repos?view=azure-devops#tfvc).

## <a name="citizen-developers"></a>Desarrolladores cívicos

Los desarrolladores profesionales son un componente fundamental de la innovación. Cuando una hipótesis muestra precisión a escala, los desarrolladores profesionales deben estabilizar y preparar la solución para la escala. La mayoría de los principios a los que se hace referencia en este artículo requerirán soporte técnico de desarrolladores profesionales. Desafortunadamente, las tendencias actuales sugieren que hay más oportunidades para desarrolladores profesionales, después están los desarrolladores. Además, el costo y el ritmo de la innovación pueden ser menos favorables cuando se requieren exigencias de desarrollo profesional. Los desarrolladores cívicos proporcionan una forma de escalar los esfuerzos de desarrollo y acelerar las primeras pruebas de hipótesis.

Los desarrolladores cívicos pueden proporcionar un enfoque inteligente cuando se pueden validar las primeras hipótesis con herramientas como [PowerApps](https://docs.microsoft.com/powerapps/powerapps-overview) para interfaces de aplicaciones, [AI Builder](/powerapps/use-ai-builder) para procesos y predicciones, [Microsoft Flow](https://docs.microsoft.com/flow) para flujos de trabajo o [Power BI](https://docs.microsoft.com/power-bi) para el consumo de datos.

> [!NOTE]
> Al aprovechar los desarrolladores cívicos para probar hipótesis, se recomienda que los desarrolladores profesionales proporcionen soporte técnico, revisión e instrucciones. Una vez que se valida una hipótesis a escala, un proceso de transición de la aplicación a un modelo de programación más sólido acelerará los ingresos de la innovación. La implicación de desarrolladores profesionales en las definiciones iniciales de procesos puede dar lugar a transiciones más limpias más adelante.

## <a name="intelligent-experiences"></a>Experiencias inteligentes

Las experiencias inteligentes combinan la velocidad y la escala de las aplicaciones web modernas, con la inteligencia de los servicios y bots cognitivos. Por sí solas, cada una de ellas puede ser suficiente para satisfacer las necesidades de los clientes. Combinadas, el espectro de las necesidades que se pueden satisfacer a través de una experiencia digital se expande, pero las inversiones en desarrollo todavía pueden contenerse.

### <a name="modern-web-apps"></a>Aplicaciones web modernas

Cuando se requiere una aplicación o una experiencia para satisfacer las necesidades de los clientes, las aplicaciones web modernas pueden ser la manera más rápida de satisfacer esas necesidades. Las experiencias web modernas pueden atraer a clientes internos o externos con rapidez y permitir una iteración rápida en la solución.

### <a name="infusing-intelligence"></a>Incorporación de inteligencia

El aprendizaje automático y la inteligencia artificial están cada vez más disponibles para los desarrolladores. La disponibilidad extendida de las API comunes con capacidades de predicción permite a los desarrolladores satisfacer mejor las necesidades del cliente a través del acceso ampliado a los datos y las predicciones.

Agregar inteligencia a una solución puede permitir la conversión de voz en texto, la traducción de texto, la visión informática e incluso la búsqueda visual. Con estas funcionalidades expandidas, es más fácil para los desarrolladores crear soluciones que aprovechen la inteligencia para crear una experiencia interactiva y moderna.

### <a name="bots"></a>Bots

Los bots proporcionan una experiencia que hace que parezca menos que se usa un equipo y más que se trata con una persona (o al menos un robot inteligente). Se pueden usar para desplazar las tareas simples y repetitivas, como reservar una mesa en un restaurante o recopilar información de un perfil, a sistemas automatizados que puede que no requieran intervención humana directa. Los usuarios conversan con los bot mediante texto, tarjetas interactivas y la voz. Una interacción con un bot puede ser tanto una pregunta y una respuesta rápidas como una conversación sofisticada que proporciona acceso a servicios de forma inteligente.

Los bots se parecen mucho a las aplicaciones web modernas, ya que residen en Internet y usan las API para enviar y recibir mensajes. El contenido de un bot varía considerablemente en función de su tipo. El software para bot moderno se basa en una pila de tecnología y herramientas que proporcionan experiencias cada vez más complejas en una amplia variedad de plataformas. Sin embargo, un bot simple simplemente puede recibir un mensaje y devolvérselo al usuario con muy poco código implicado.

Los bots puede hacer lo mismo que otros tipos de software (leer y escribir archivos, usar bases de datos y API, y realizar las tareas de cálculo habituales). Lo que hace que los bots sean únicos es su uso de mecanismos que generalmente se reservan para la comunicación entre humanos.

## <a name="cloud-native-solutions"></a>Soluciones nativas de la nube

Las aplicaciones nativas de la nube se crean desde cero. Las aplicaciones nativas de la nube se optimizan para la escala y el rendimiento de la nube. Las aplicaciones nativas de la nube se crean normalmente mediante enfoques de microservicios, sin servidor, basados en eventos o basados en contenedores. Normalmente, las soluciones nativas de la nube aprovechan una combinación de arquitecturas de microservicios, servicios administrados y entrega continua para lograr confiabilidad y acelerar el tiempo de comercialización.

Una solución nativa de la nube permite a los equipos de desarrollo centralizados mantener el control de la lógica de negocios, sin necesidad de soluciones centralizadas monolíticas. Este tipo de solución también crea un marcador para impulsar la coherencia entre los desarrolladores cívicos y las experiencias modernas. Por último, las soluciones nativas de la nube proporcionan un acelerador de la innovación al dar libertad a los desarrolladores cívicos y profesionales para innovar de manera segura y con bloqueos mínimos.

## <a name="innovate-through-existing-solutions"></a>Innovar a través de soluciones existentes

Muchas hipótesis de clientes se pueden entregar mejor mediante una versión modernizada de una solución existente. Cuando la lógica de negocios actual satisface las necesidades del cliente (o casi), es posible que pueda acelerar la innovación mediante la creación sobre una solución modernizada.

La mayoría de las formas de modernización, incluida la leve refactorización de la aplicación, se incluyen en la [metodología de la migración](../../migrate/index.md) dentro del marco de adopción de la nube. Esa metodología guía a los equipos de adopción de la nube a través de los procesos de migración de un [estado digital](../../digital-estate/index.md) a la nube. La [Guía de migración a Azure](../../migrate/azure-migration-guide/index.md) proporciona un enfoque simplificado de la misma metodología, que es adecuada para un número reducido de cargas de trabajo o incluso una sola aplicación.

Una vez migrada y modernizada, hay varias formas de aprovechar la solución en la creación de nuevas soluciones innovadoras para las necesidades de los clientes. Por ejemplo, los [desarrolladores cívicos](#citizen-developers) podrían probar las hipótesis o los desarrolladores profesionales podrían crear [experiencias inteligentes](#intelligent-experiences) o [soluciones nativas de la nube](#cloud-native-solutions).

### <a name="extend-an-existing-solution"></a>Ampliar una solución existente

La ampliación de una solución es una forma común de modernización. Este enfoque puede ser la ruta más rápida a la innovación cuando se cumplen las siguientes condiciones de la hipótesis del cliente:

- La lógica de negocios existente debe satisfacer (o casi) la necesidad existente del cliente.
- Una experiencia mejorada satisfaría mejor las necesidades de una cohorte de clientes específica.
- La lógica de negocios que requiere la solución de MVP se ha centralizado, normalmente a través de un diseño de [n niveles](/azure/architecture/guide/architecture-styles/n-tier), servicios web, API o [microservicios](/azure/architecture/guide/architecture-styles/microservices). Este enfoque consiste en encapsular la solución existente con una nueva experiencia hospedada en la nube. En Azure, esta solución probablemente residiría en Azure App Services.

### <a name="rebuild-an-existing-solution"></a>Volver a crear una solución existente

Si una aplicación no se puede ampliar fácilmente, puede que sea necesario refactorizar la solución. En este enfoque, la carga de trabajo se migra a la nube. Una vez migrada, se modifican o duplican partes de la aplicación, como servicios web o [microservicios](/azure/architecture/guide/architecture-styles/microservices), que se implementan en paralelo a la solución existente. La solución paralela basada en servicio podría tratarse como una solución ampliada. Esta solución simplemente encapsularía la solución existente con una nueva experiencia hospedada en la nube. En Azure, esta solución probablemente residiría en Azure App Services.

> [!CAUTION]
> La refactorización o la rearquitectura de soluciones o la centralización de la lógica de negocios puede convertirse rápidamente en un [pico técnico](./build.md#reduce-complexity-and-delay-technical-spikes) prolongado, en lugar de un origen de valor de cliente. Es un riesgo de la innovación, especialmente en la validación de hipótesis. Con un poco de creatividad en el diseño de una solución, debe haber una ruta a MVP que no requiera la refactorización de las soluciones existentes. Es aconsejable retrasar la refactorización, hasta que se pueda validar la hipótesis inicial a escala.

## <a name="operating-model-innovations"></a>Innovaciones del modelo operativo

Además de los enfoques de innovación modernos para la creación de aplicaciones, se han producido innovaciones en cuanto a las operaciones de las aplicaciones. Los enfoques han generado muchos movimientos de la organización. Uno de los más destacados es el traslado hacia modelos operativos de [centro de excelencia en la nube](../../organize/cloud-center-of-excellence.md). Los equipos empresariales, cuando están provistos de personal y consolidados, tienen la opción de proporcionar su propio soporte técnico operativo para una solución.

El tipo de modelo de administración operativa de autoservicio, que se encuentra en un centro de excelencia en la nube, permite controles más estrictos e iteraciones más rápidas dentro del entorno de la solución. Esto se logra mediante la transferencia del control operativo y la responsabilidad al equipo empresarial.

Cuando el objetivo es escalar o satisfacer la demanda global de una solución existente, este enfoque puede ser suficiente para validar una hipótesis de cliente. Una vez migradas y ligeramente modernizadas, el equipo empresarial tendrá la capacidad de escalar soluciones para probar una variedad de hipótesis con respecto a las cohortes de clientes que se preocupan por el rendimiento, la distribución global u otras necesidades de los clientes que se ven obstaculizadas por operaciones de TI.

## <a name="reduce-overhead-and-management"></a>Reducir la sobrecarga y la administración

Cuantos más elementos se tengan que mantener en una solución, más lenta iterará la solución. Acelere la innovación mediante la reducción del impacto que las operaciones tienen en la velocidad disponible.

Para prepararse para el número de iteraciones necesarias para ofrecer una solución innovadora, es importante anticiparse. Minimice las cargas operativas al principio del proceso, favoreciendo las opciones sin servidor.

En Azure, las opciones de aplicación sin servidor podrían incluir [Azure App Service](https://docs.microsoft.com/azure/app-service/overview) o [contenedores](https://docs.microsoft.com/azure/architecture/cloud-adoption/migrate/azure-best-practices/contoso-migration-rearchitect-container-sql).

En paralelo, Azure proporciona opciones de datos de transacciones sin servidor que también reducen la sobrecarga. La [lista de productos de base de datos](https://docs.microsoft.com/azure/#pivot=products&panel=databases) proporciona opciones para hospedar datos, sin necesidad de una plataforma de datos completa.

## <a name="next-steps"></a>Pasos siguientes

En función de la hipótesis y la solución, los principios de este artículo pueden ayudar a diseñar aplicaciones que cumplan con las definiciones de MVP e interaccionen con los usuarios. A continuación, se indican los principios de [capacitación para la adopción](./ci-cd.md), que explican las formas para que la aplicación y los datos se encuentren en las manos de los clientes más rápidamente.

> [!div class="nextstepaction"]
> [Capacitación para la adopción](./ci-cd.md)
