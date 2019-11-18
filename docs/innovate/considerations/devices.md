---
title: 'Innovación en la nube: Interacción con dispositivos'
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: 'Introducción a la innovación en la nube: interacción con dispositivos'
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: innovate
ms.openlocfilehash: 4a1b96a5f29ebac9fd228ab1603d12e08b38ba63
ms.sourcegitcommit: 6f287276650e731163047f543d23581d8fb6e204
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73752089"
---
# <a name="ambient-experiences-interact-with-devices"></a>Experiencias ambientales: Interacción con dispositivos

En [Creación con la empatía de los clientes](./build.md), analizamos las tres pruebas de una verdadera innovación: Solucionar las necesidades de un cliente, hacer que el cliente vuelva y aumentar la cartera de cohortes de clientes. Probar cada hipótesis requiere trabajo e iteraciones en el enfoque de la adopción. En este artículo se proporciona información detallada sobre algunos enfoques avanzados para reducir ese trabajo mediante *experiencias ambientales*. Al interactuar con dispositivos en lugar de hacerlo con una aplicación, es posible que el cliente tenga más probabilidades de acudir primero a su solución.

## <a name="ambient-experiences"></a>Experiencias ambientales

Una experiencia ambiental es una experiencia digital que está relacionada con el entorno inmediato. Una solución que ofrece experiencias ambientales se esfuerza por satisfacer al cliente en el momento que lo necesita. Siempre que es posible, la solución satisface las necesidades del cliente sin abandonar el flujo de actividades que la provocó.

La vida en la economía digital está llena de distracciones. A todos nos bombardean con mensajes de redes sociales, correo electrónico, web, visuales y verbales, y cada uno de estos elementos supone una posibilidad de distracción. Este riesgo aumenta con cada segundo que transcurre entre el momento que se produce la necesidad del cliente y el momento en que se encuentra una solución. Innumerables clientes se pierden en ese breve intervalo de tiempo. Para fomentar una mayor adopción reiterada, debe reducir el tiempo de solución (TTS) y así disminuirá también el número de distracciones.

## <a name="interacting-with-devices"></a>Interacción con los dispositivos

Una experiencia web estándar es la técnica de desarrollo de aplicaciones más común que se usa para satisfacer las necesidades de un cliente. En este enfoque se supone que el cliente está delante de su equipo. Si el cliente satisface constantemente su necesidad con su portátil, cree una aplicación web. Esa aplicación web proporcionará una experiencia ambiental para ese cliente, en ese escenario. Sin embargo, sabemos que este escenario cada vez es menos probable en nuestros días.

![Experiencias ambientales](../../_images/innovate/ambient-experiences.png)

Hoy en día, las experiencias ambientales normalmente requieren más de una aplicación web. Mediante la [medición](./measure.md) y el [aprendizaje con el cliente](./learn.md), el comportamiento que desencadena la necesidad del cliente se puede observar, controlar y usar para crear una experiencia ambiental más adecuada. En la siguiente lista se resumen algunos enfoques para integrar soluciones ambientales en sus hipótesis con más información sobre cada una de ellas en los párrafos siguientes.

- **[Experiencia con dispositivos móviles](#mobile-experience):** al igual que con los equipos portátiles, las aplicaciones móviles están omnipresentes en los entornos de clientes. En algunas situaciones, esto puede proporcionar un nivel suficiente de interactividad para crear una solución ambiental.
- **[Realidad mixta:](#mixed-reality):** a veces, el entorno típico de un cliente debe modificarse para conformar un ambiente de interacción. Este factor crea una suerte de realidad falsa en la que el cliente interactúa con la solución y se resuelve una de sus necesidades. En este caso, la solución es un ambiente dentro de la realidad falsa.
- **[Realidad integrada](#integrated-reality):** al aproximarse a un ambiente real, las soluciones de realidad integrada se centran en el uso de un dispositivo que existe dentro de la realidad del cliente para integrar la solución en comportamientos naturales. Un asistente virtual es un buen ejemplo de integración de la realidad en el entorno circundante. Una opción menos conocida es el uso de tecnologías de Internet de las cosas (IoT) que integran dispositivos que ya existen en el entorno del cliente.
- **[Realidad ajustada](#adjusted-reality):** cuando alguna de las soluciones ambientales anteriores usa el análisis predictivo en la nube para definir y proporcionar una interacción con el cliente dentro de su entorno natural, la solución incluye realidad ajustada.

Comprender la necesidad del cliente y cuantificar los efectos en él contribuirá a determinar si se va a requerir la interacción de un dispositivo o una experiencia ambiental para comprobar su hipótesis. Las secciones siguientes le ayudarán a encontrar la mejor solución para cada uno de esos puntos de datos.

## <a name="mobile-experience"></a>Experiencia móvil

En la primera fase de la experiencia ambiental, el usuario se aleja del equipo. Los consumidores y los profesionales de la actualidad se mueven con fluidez entre dispositivos móviles y PC. Cada una de las plataformas o dispositivos usados por el cliente crea una nueva experiencia potencial. Agregar una experiencia móvil que amplíe la solución principal es la forma más rápida de mejorar la integración en el entorno inmediato del cliente. Aunque un dispositivo móvil esté lejos del ambiente, podría estar más próximo a la necesidad del cliente.

Cuando los clientes cambian de ubicación con frecuencia, puede ser la forma más pertinente de experiencia ambiental para una solución concreta. En la última década, la integración de las soluciones existentes con una experiencia móvil ha desencadenado frecuentemente la innovación.

Azure App Service es un buen ejemplo de este enfoque. Durante las primeras iteraciones, se puede usar la [característica de aplicación web de Azure App Service](https://docs.microsoft.com/azure/app-service/overview) para probar la hipótesis. A medida que las hipótesis se vuelven más complejas, la [característica de aplicación móvil de Azure App Services](https://docs.microsoft.com/azure/app-service-mobile) puede ampliar la aplicación web para que se ejecute en diversas plataformas móviles.

## <a name="mixed-reality"></a>Realidad mixta

Las soluciones de realidad mixta representan el siguiente nivel de consolidación de las experiencias ambientales. Este enfoque aumenta o replica el entorno del cliente y crea una extensión de la realidad para que el cliente trabaje dentro de ella.

> [!IMPORTANT]
> Si se requiere un dispositivo de realidad virtual y *todavía no forma parte de los comportamientos naturales o circundantes inmediatos de un cliente*, la realidad virtual o aumentada es más una experiencia alternativa y menos una experiencia ambiental.

Las experiencias de realidad mixta son cada vez más habituales entre los empleados remotos. Su uso está creciendo aún más rápido en sectores que requieren conocimientos de colaboración o especializados que no están disponibles en el mercado local. Las situaciones que requieren la implementación centralizada de un producto complejo para un grupo de empleados remotos son un terreno especialmente adecuado para la realidad aumentada. En esos casos, el equipo de soporte técnico central y los empleados remotos pueden usar la realidad aumentada para solucionar problemas, instalar el producto o trabajar con él.

Por ejemplo, considere el caso de los anclajes espaciales. Los anclajes espaciales le permiten crear experiencias de realidad mixta con objetos cuyas ubicaciones correspondientes persisten en todos los dispositivos a lo largo del tiempo. Los anclajes espaciales se usan para capturar, grabar y conservar un comportamiento específico, que proporcionará una experiencia ambiental la próxima vez que el usuario trabaje dentro de ese entorno aumentado. [Azure Spatial Anchors](https://docs.microsoft.com/azure/spatial-anchors/overview) es un servicio que pasa esta lógica a la nube, lo que permite compartir experiencias entre dispositivos e incluso entre soluciones.

## <a name="integrated-reality"></a>Realidad integrada

La realidad integrada va más allá de la realidad móvil o incluso de la realidad mixta. La realidad integrada pretende eliminar por completo la experiencia digital. Todos los dispositivos que usamos tienen funcionalidades de conectividad y proceso. Estos dispositivos se pueden usar para recopilar datos del entorno inmediato sin que el cliente tenga que tocar un teléfono, un portátil o un dispositivo de realidad virtual.

Esta experiencia es ideal cuando una forma de dispositivo es coherente en el mismo entorno en el que se produce la necesidad del cliente. Entre los escenarios comunes se incluyen las fábricas, los ascensores o incluso su automóvil. Estos tipos de dispositivos grandes ya contienen potencia de proceso. También puede usar datos del propio dispositivo para detectar los comportamientos del cliente y enviarlos a la nube. Esta captura automática de los datos de comportamiento del cliente reduce drásticamente la necesidad de que un cliente escriba datos. Además, la experiencia web, móvil o de realidad virtual puede funcionar como un bucle de comentarios para compartir lo que se ha aprendido de la solución de realidad integrada.

Entre los ejemplos de realidad integrada en Azure se incluyen:

- [Soluciones de Internet de las cosas (IoT) de Azure](https://docs.microsoft.com/azure/iot-fundamentals), una colección de servicios de Azure que ayudan a administrar los dispositivos y el flujo de datos desde esos dispositivos hacia la nube y de vuelta a los usuarios finales.
- [Azure Sphere](https://docs.microsoft.com/azure-sphere), una combinación de hardware y software. Azure Sphere es una manera intrínsecamente segura que permite la transmisión de datos segura entre un dispositivo existente y las soluciones de Azure IoT.
- [Azure Kinect Developers Kit](https://docs.microsoft.com/azure/Kinect-dk), sensores de inteligencia artificial con modelos avanzados de Computer Vision y de voz. Estos sensores pueden recopilar datos visuales y de audio del entorno inmediato y alimentan la solución con esas entradas.

Puede usar las tres herramientas para recopilar datos del entorno natural y en el momento en que se produce la necesidad del cliente. A partir de ahí, la solución puede responder a esas entradas de datos para resolver la necesidad, a veces antes de que el cliente sea consciente de que se ha desencadenado esa necesidad.

## <a name="adjusted-reality"></a>Realidad ajustada

La forma más refinada de experiencia ambiental es la realidad ajustada, también conocida como *inteligencia ambiental*. La realidad ajustada es un enfoque relacionado con el uso de la información de la solución para cambiar la realidad del cliente sin que este tenga que interactuar directamente con una aplicación. En este enfoque, la aplicación que creó inicialmente para demostrar su hipótesis puede que ya no sea pertinente. En su lugar, los dispositivos del entorno ayudarían a modular las entradas y salidas para satisfacer las necesidades de los clientes.

Los asistentes virtuales o altavoces inteligentes son un buen ejemplo de realidad ajustada. Por sí mismo, un altavoz inteligente es un ejemplo de realidad integrada simple. Agregue una luz inteligente y un sensor de movimiento a una solución de altavoz inteligente, y habrá creado fácilmente una solución básica que encienda las luces cuando se entra en una habitación.

Las fábricas de todo el mundo constituyen otros ejemplos de realidad ajustada. En las primeras fases de la realidad integrada, los sensores de los dispositivos detectaban condiciones como un sobrecalentamiento, y la notificaban a un ser humano mediante una aplicación. En la realidad ajustada, el cliente podría seguir participando, pero el bucle de comentarios es más estrecho. En una fábrica con realidad ajustada, un dispositivo podría detectar el sobrecalentamiento de una máquina vital en alguna parte de la línea de montaje. En cualquier otra parte de la planta, un segundo dispositivo ralentizaría la producción ligeramente para permitir que la máquina se enfriara y el ritmo se reanudara cuando se resolviera la condición. En esta situación, el cliente es un participante de segunda mano. El cliente utiliza la aplicación para establecer las reglas y entender cómo han afectado a la producción, pero no sería una parte necesaria del bucle de comentarios.

Los servicios de Azure que se describen en [Soluciones de Internet de las cosas (IoT) de Azure](https://docs.microsoft.com/azure/iot-fundamentals), [Azure Sphere](https://docs.microsoft.com/azure-sphere) y [Azure Kinect Developers Kit](https://docs.microsoft.com/azure/Kinect-dk) podrían ser componentes de una solución de realidad ajustada. La aplicación original y la lógica de negocios serviría como intermediario entre la entrada del entorno y el cambio que se debe realizar en el entorno físico.

Un gemelo digital es otro ejemplo de realidad ajustada. Este término se refiere a una representación digital de un dispositivo físico que se presenta mediante equipos, dispositivos móviles o formatos de realidad mixta. A diferencia de los modelos 3D menos sofisticados, un gemelo digital refleja los datos recopilados de un dispositivo real en el entorno físico. Esta solución permite al usuario interactuar con la representación digital de maneras que nunca podrían darse en el mundo real. En este enfoque, los dispositivos físicos ajustan un entorno de realidad mixta. Sin embargo, la solución sigue recopilando datos de una solución de realidad integrada y usándolos para dar forma a la realidad del entorno actual del cliente.

En Azure, se crean gemelos digitales y se accede a ellos con un servicio llamado [Azure Digital Twins](https://docs.microsoft.com/azure/digital-twins/about-digital-twins).

## <a name="next-steps"></a>Pasos siguientes

Ahora que conoce mejor las interacciones con los dispositivos y la experiencia ambiental adecuada para su solución, ya está preparado para explorar la materia final de innovación: [predicción e influencia](./predict.md).

> [!div class="nextstepaction"]
> [Predicción e influencia](./predict.md)
