---
title: Participación mediante aplicaciones en la invención digital
description: Comprenda cómo crear aplicaciones que modelen datos y que creen experiencias que permitan participar a los clientes y respalden la innovación.
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: innovate
ms.openlocfilehash: c482c6a9642e1de3f28bbe650da6fa43cf9229be
ms.sourcegitcommit: ea63be7fa94a75335223bd84d065ad3ea1d54fdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80356770"
---
# <a name="engage-through-applications"></a>Participación mediante aplicaciones

Tal y como se describe en [Democratización de los datos](./data.md), los datos son el nuevo petróleo. Alimentan la mayoría de las innovaciones en la economía digital. Según esta analogía, las aplicaciones serían las estaciones de servicio y la infraestructura necesaria para que dicho combustible llegue a las manos adecuadas.

En algunos casos, los datos por sí mismos son suficientes para producir un cambio y satisfacer las necesidades de los clientes. Sin embargo, lo más frecuente es que la solución para las necesidades de los clientes requiera aplicaciones para dar forma a los datos y crear una experiencia. Las aplicaciones son la manera de interactuar con el usuario. Son el inicio de los procesos necesarios para responder a los desencadenantes de los clientes. Son los medios que tienen los clientes para proporcionar datos y recibir instrucciones. En este artículo se resumen varios principios que pueden ayudarle a alinearse con la solución de aplicación correcta, en función de la hipótesis que se vaya a validar.

![Participación mediante aplicaciones](../../_images/innovate/engage-via-apps.png)

## <a name="shared-code"></a>Código compartido

Los equipos que responden con mayor rapidez y precisión a los comentarios de los clientes, a los cambios en el mercado y a las oportunidades de innovación normalmente liderarán sus respectivos mercados en la innovación. El primer principio de las aplicaciones innovadoras se resume en la [información general sobre la mentalidad de crecimiento](./learn.md#growth-mindset): "Compartir el código". Con el tiempo, la innovación emerge de un foco cultural. Para sostener la innovación, se necesitan diferentes perspectivas y contribuciones.

Para estar preparado para la innovación, todo el desarrollo de aplicaciones debe comenzar por un repositorio de código compartido. La herramienta más adoptada para administrar los repositorios de código es [GitHub](https://guides.github.com), que permite crear rápidamente un repositorio de código compartido. También existe [Azure Repos](https://docs.microsoft.com/azure/devops/repos/get-started/what-is-repos?view=azure-devops), un conjunto de herramientas de control de versiones en Azure DevOps Services que se puede usar para administrar el código. Azure Repos proporciona dos tipos de control de versiones:

- [Git](https://docs.microsoft.com/azure/devops/repos/get-started/what-is-repos?view=azure-devops#git): control de versiones distribuido
- [Control de versiones de Team Foundation (TFVC)](https://docs.microsoft.com/azure/devops/repos/get-started/what-is-repos?view=azure-devops#tfvc): control de versiones centralizado

## <a name="citizen-developers"></a>Desarrolladores cívicos

Los desarrolladores profesionales son un componente fundamental de la innovación. Cuando una hipótesis muestra precisión a escala, los desarrolladores profesionales deben estabilizar y preparar la solución para la escala. La mayoría de los principios a los que se hace referencia en este artículo requieren soporte técnico de desarrolladores profesionales. Desafortunadamente, las tendencias actuales sugieren que hay una mayor demanda para desarrolladores profesionales que existencia de desarrolladores. Además, el costo y el ritmo de la innovación pueden ser menos favorables cuando se considera necesario el desarrollo profesional. En respuesta a estos desafíos, desarrolladores cívicos proporcionan una forma de escalar los esfuerzos de desarrollo y acelerar las primeras pruebas de hipótesis.

El uso de desarrolladores cívicos puede resultar viable y efectivo cuando se pueden validar las primeras hipótesis con herramientas como [PowerApps](https://docs.microsoft.com/powerapps/powerapps-overview) para interfaces de aplicaciones, [AI Builder](https://docs.microsoft.com/powerapps/use-ai-builder) para procesos y predicciones, [Microsoft Flow](https://docs.microsoft.com/flow) para flujos de trabajo y [Power BI](https://docs.microsoft.com/power-bi) para el consumo de datos.

> [!NOTE]
> Cuando confía en desarrolladores cívicos para probar hipótesis, se recomienda tener a la mano algunos desarrolladores profesionales para proporcionar soporte técnico, revisión e instrucciones. Después de validar una hipótesis a escala, un proceso de transición de la aplicación a un modelo de programación más sólido acelerará los ingresos de la innovación. Al implicar a desarrolladores profesionales al principio de las definiciones de procesos, puede lograr transiciones más limpias más adelante.

## <a name="intelligent-experiences"></a>Experiencias inteligentes

Las experiencias inteligentes combinan la velocidad y la escala de las aplicaciones web modernas, con la inteligencia de los servicios y bots cognitivos. Por sí solas, cada una de estas tecnologías puede bastar para satisfacer las necesidades de los clientes. Cuando se combinan de forma inteligente, amplían el espectro de necesidades que se pueden satisfacer a través de una experiencia digital, a la vez que ayudan a contener los costos de desarrollo.

### <a name="modern-web-apps"></a>Aplicaciones web modernas

Cuando se requiere una aplicación o una experiencia para satisfacer las necesidades de los clientes, las aplicaciones web modernas pueden ser la manera más rápida de hacerlo. Las experiencias web modernas pueden atraer a clientes internos o externos con rapidez y permitir una iteración rápida en la solución.

### <a name="infusing-intelligence"></a>Incorporación de inteligencia

El aprendizaje automático y la inteligencia artificial cada vez están más disponibles para los desarrolladores. La disponibilidad extendida de las API comunes con capacidades de predicción permite a los desarrolladores satisfacer mejor las necesidades del cliente a través del acceso ampliado a los datos y las predicciones.

Agregar inteligencia a una solución puede permitir la conversión de voz en texto, la traducción de texto, la visión informática e incluso la búsqueda visual. Con estas funcionalidades expandidas, es más fácil para los desarrolladores crear soluciones que aprovechan la inteligencia para crear una experiencia interactiva y moderna.

### <a name="bots"></a>Bots

Los bots proporcionan una experiencia que hace que parezca menos que se usa un equipo y más que se trata con una persona (como mínimo, con un robot inteligente). Se pueden usar para desplazar las tareas simples y repetitivas (como reservar una mesa en un restaurante o recopilar información de un perfil) a sistemas automatizados que puede que no requieran intervención humana directa. Los usuarios conversan con los bot a través de texto, tarjetas interactivas y la voz. Una interacción con un bot puede ir de una pregunta y una respuesta rápidas a una conversación sofisticada que proporciona acceso a servicios de forma inteligente.

Los bots se parecen mucho a las aplicaciones web modernas: residen en Internet y usan las API para enviar y recibir mensajes. El contenido de un bot varía considerablemente en función de su tipo. El software para bot moderno se basa en una pila de tecnología y herramientas que proporcionan experiencias cada vez más complejas en varias plataformas. Sin embargo, un bot simple simplemente puede recibir un mensaje y devolvérselo al usuario con muy poco código implicado.

Los bots puede hacer lo mismo que otros tipos de software: leer y escribir archivos, usar bases de datos y API y realizar las tareas de cálculo habituales. Lo que hace que los bots sean únicos es su uso de mecanismos que generalmente se reservan para la comunicación entre humanos.

## <a name="cloud-native-solutions"></a>Soluciones nativas de la nube

Las aplicaciones nativas de la nube se crean desde cero y están optimizadas para la escala y el rendimiento de la nube. Las aplicaciones nativas de la nube se crean normalmente mediante enfoques de microservicios, sin servidor, basados en eventos o basados en contenedores. Normalmente, las soluciones nativas de la nube usan una combinación de arquitecturas de microservicios, servicios administrados y entrega continua para lograr confiabilidad y acelerar el tiempo de comercialización.

Una solución nativa de la nube permite a los equipos de desarrollo centralizados mantener el control de la lógica de negocios, sin necesidad de soluciones centralizadas monolíticas. Este tipo de solución también crea un marcador para impulsar la coherencia entre las entradas de los desarrolladores cívicos y las experiencias modernas. Por último, las soluciones nativas de la nube proporcionan un acelerador de la innovación al dar libertad a los desarrolladores cívicos y profesionales para innovar de manera segura y con un mínimo de bloqueos.

## <a name="innovate-through-existing-solutions"></a>Innovar a través de soluciones existentes

Muchas hipótesis de clientes se pueden entregar mejor mediante una versión modernizada de una solución existente. Cuando la lógica de negocios actual satisface las necesidades del cliente (o casi), puede acelerar la innovación mediante la creación sobre una solución modernizada.

La mayoría de las formas de modernización, incluida la leve refactorización de la aplicación, se incluyen en la [metodología de la migración](../../migrate/index.md) dentro del marco de adopción de la nube. Esa metodología guía a los equipos de adopción de la nube a través del proceso de migración de un [estado digital](../../digital-estate/index.md) a la nube. La [Guía de migración a Azure](../../migrate/azure-migration-guide/index.md) proporciona un enfoque simplificado de la misma metodología, que es adecuada para un número reducido de cargas de trabajo o incluso una sola aplicación.

Después de migrar y modernizar una solución, hay varias formas de usarla en la creación de nuevas soluciones innovadoras para las necesidades de los clientes. Por ejemplo, los [desarrolladores cívicos](#citizen-developers) podrían probar las hipótesis o los desarrolladores profesionales podrían crear [experiencias inteligentes](#intelligent-experiences) o [soluciones nativas de la nube](#cloud-native-solutions).

### <a name="extend-an-existing-solution"></a>Ampliar una solución existente

La ampliación de una solución es una forma común de modernización. Este enfoque puede ser la ruta más rápida a la innovación cuando se cumplen las siguientes condiciones de la hipótesis del cliente:

- La lógica de negocios existente debe satisfacer (o casi) la necesidad existente del cliente.
- Una experiencia mejorada satisfaría mejor las necesidades de una cohorte de clientes específica.
- La lógica de negocios que requiere la solución de producto mínimo viable (MVP) se ha centralizado, normalmente a través de un diseño de [n niveles](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/n-tier), servicios web, API o [microservicios](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices). Este enfoque consiste en encapsular la solución existente dentro de una nueva experiencia hospedada en la nube. En Azure, esta solución probablemente residiría en Azure App Services.

### <a name="rebuild-an-existing-solution"></a>Volver a crear una solución existente

Si una aplicación no se puede ampliar fácilmente, puede que sea necesario refactorizar la solución. En este enfoque, la carga de trabajo se migra a la nube. Después de migrar la aplicación, se modifican o duplican partes de esta, como servicios web o [microservicios](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices), que se implementan en paralelo a la solución existente. La solución paralela basada en servicio podría tratarse como una solución ampliada. Esta solución simplemente encapsularía la solución existente con una nueva experiencia hospedada en la nube. En Azure, esta solución probablemente residiría en Azure App Services.

> [!CAUTION]
> La refactorización o la rearquitectura de soluciones o la centralización de la lógica de negocios puede desencadenar rápidamente un [pico técnico](./build.md#reduce-complexity-and-delay-technical-spikes) prolongado, en lugar de una fuente de valor para el cliente. Es un riesgo de la innovación, especialmente en la validación de hipótesis. Con un poco de creatividad en el diseño de una solución, debe haber una ruta a MVP que no requiera la refactorización de las soluciones existentes. Es aconsejable retrasar la refactorización, hasta que se pueda validar la hipótesis inicial a escala.

## <a name="operating-model-innovations"></a>Innovaciones del modelo operativo

Además de los enfoques modernos e innovadores para la creación de aplicaciones, se han producido innovaciones importantes en las *operaciones* de aplicaciones. Estos enfoques han generado muchos movimientos de la organización. Uno de los más destacados es el modelo operativo de [centro de excelencia en la nube](../../organize/cloud-center-of-excellence.md). Los equipos empresariales, cuando están provistos de personal y consolidados, tienen la opción de proporcionar su propio soporte técnico operativo para una solución.

El tipo de modelo de administración operativa de autoservicio, que se encuentra en un centro de excelencia en la nube, permite controles más estrictos e iteraciones más rápidas dentro del entorno de la solución. Estas metas se logran mediante la transferencia del control operativo y la responsabilidad al equipo empresarial.

Si intenta escalar o satisfacer la demanda global de una solución existente, este enfoque puede ser suficiente para validar una hipótesis de cliente. Una vez que una solución se migra y se moderniza ligeramente, el equipo empresarial puede escalarla para probar una variedad de hipótesis. Normalmente implican a los cohortes de los clientes que están preocupados por el rendimiento, la distribución global y otras necesidades de los clientes que se ven entorpecidas por las operaciones de TI.

## <a name="reduce-overhead-and-management"></a>Reducir la sobrecarga y la administración

Cuantos más elementos se tengan que mantener en una solución, más lenta iterará la solución. Esto implica que puede acelerar la innovación al reducir el impacto de las operaciones en el ancho de banda disponible.

Para prepararse para el número de iteraciones necesarias para ofrecer una solución innovadora, es importante anticiparse. Por ejemplo, minimice las cargas operativas al principio del proceso, favoreciendo las opciones sin servidor. En Azure, las opciones de aplicación sin servidor podrían incluir [Azure App Service](https://docs.microsoft.com/azure/app-service/overview) o [contenedores](https://docs.microsoft.com/azure/architecture/cloud-adoption/migrate/azure-best-practices/contoso-migration-rearchitect-container-sql).

En paralelo, Azure proporciona opciones de datos de transacciones sin servidor que también reducen la sobrecarga. El [catálogo de productos de Azure](https://docs.microsoft.com/azure) proporciona opciones de base de datos que hospedan datos sin necesidad de una plataforma de datos completa.

## <a name="next-steps"></a>Pasos siguientes

En función de la hipótesis y la solución, los principios de este artículo pueden ayudar a diseñar aplicaciones que cumplan con las definiciones de MVP e interaccionen con los usuarios. A continuación, se indican los principios de [capacitación para la adopción](./ci-cd.md), que ofrecen formas de poner la aplicación y los datos en las manos de los clientes de forma más rápida y eficiente.

> [!div class="nextstepaction"]
> [Capacitación para la adopción](./ci-cd.md)
