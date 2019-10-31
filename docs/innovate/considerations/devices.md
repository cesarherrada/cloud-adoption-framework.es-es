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
ms.openlocfilehash: 5a9ec9f38d89683482d7f98923aa0ef2ccf201b9
ms.sourcegitcommit: f3371811a36e12533ecbc3aa936e2a68e0cee25f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2019
ms.locfileid: "72683227"
---
# <a name="ambient-experiences-interact-with-devices"></a>Experiencias ambientales: Interacción con dispositivos

En [crear con empatía](./build.md), analizamos las tres pruebas de una verdadera innovación: solucionar las necesidades de un cliente, hacer que el cliente vuelva y aumentar la cartera de clientes. Probar cada hipótesis requerirá trabajo e iteraciones en el enfoque de la adopción. En este artículo se proporciona información detallada sobre algunos enfoques avanzados para reducir ese trabajo mediante **experiencias ambientales**. Al interactuar con dispositivos en lugar de hacerlo con una aplicación, es posible que el cliente tenga más probabilidades de acudir primero a su solución para satisfacer sus necesidades.

## <a name="ambient-experiences"></a>Experiencias ambientales

Una experiencia ambiental es una experiencia digital que está relacionada con el entorno inmediato. Una solución que ofrece experiencias ambientales se esfuerza por satisfacer al cliente en el momento que lo necesita. Siempre que sea posible, la solución satisface las necesidades del cliente sin abandonar el flujo natural de lo que estaba haciendo.

La vida en la economía digital está llena de distracciones. A todos nos bombardean con mensajes de redes sociales, correo electrónico, web, visuales y verbales, y cada uno de estos elementos supone una posibilidad de distracción. El riesgo de distracción aumenta con cada segundo que transcurre entre que el cliente siente una necesidad y el momento en que interacciona con la solución. Innumerables clientes se pierden en ese breve intervalo de tiempo. Para fomentar una mayor adopción reiterada, reduzca el tiempo de solución (TTS) y así disminuirá también el número de distracciones.

## <a name="interacting-with-devices"></a>Interacción con los dispositivos

Una experiencia web estándar es la técnica de desarrollo de aplicaciones más común que se usa para satisfacer las necesidades de un cliente. La hipótesis que se incorpora a este enfoque es que el cliente estará delante de su equipo. Si el cliente satisface constantemente su necesidad con su portátil, cree una aplicación web. Esa aplicación web proporcionará una "experiencia ambiental" para ese cliente, en ese escenario. Sin embargo, sabemos que este escenario es cada vez menos probable en la sociedad moderna.

![Experiencias ambientales](../../_images/innovate/ambient-experiences.png)

Las experiencias ambientales, como se muestra arriba, normalmente requieren más de una aplicación web. A través de la [medición](./measure.md) y el [aprendizaje con el cliente](./learn.md), el comportamiento que conduce a la activación de una necesidad en el cliente se puede observar, controlar y usar para crear una experiencia ambiental más adecuada. A continuación, se resumen algunos enfoques para integrar soluciones ambientales en sus hipótesis. Encontrará más información sobre cada uno en los párrafos siguientes.

- **[Experiencia con dispositivos móviles:](#mobile-experience)** : al igual que un portátil, las aplicaciones móviles suelen formar parte del entorno de los clientes. En algunos escenarios, esto puede proporcionar un nivel suficiente de interactividad para crear una solución ambiental.
- **[Realidad mixta:](#mixed-reality):** a veces, el entorno natural de un cliente debe modificarse para conformar un ambiente de interacción. Así se crea una suerte de realidad falsa en la que el cliente puede interactuar con la solución y satisfacer una necesidad. En este caso, la solución es un ambiente dentro de la realidad falsa.
- **[Realidad integrada](#integrated-reality):** al aproximarse a un ambiente real, las soluciones de realidad integrada se centran en el uso de un dispositivo que existe dentro de la realidad del cliente para integrar la solución en comportamientos naturales. Un asistente virtual es un buen ejemplo de integración de la realidad en el entorno circundante. Una opción menos conocida es el uso de tecnologías de Internet de las cosas (IoT) para integrar dispositivos que ya existen en el entorno del cliente.
- **[Realidad ajustada](#adjusted-reality):** cuando alguna de las soluciones ambientales anteriores usa el análisis predictivo en la nube para definir y proporcionar una interacción con el cliente dentro de su entorno natural, la solución incluye realidad ajustada.

Comprender la necesidad del cliente y cuantificar los efectos en él contribuirá a determinar si se va a requerir la interacción de un dispositivo o una experiencia ambiental para comprobar su hipótesis. En el caso de cada uno de estos datos, las secciones siguientes le ayudarán a encontrar la mejor solución.

## <a name="mobile-experience"></a>Experiencia móvil

La primera fase de la experiencia ambiental es alejarse del equipo. Los consumidores y los profesionales de la actualidad se mueven con fluidez entre dispositivos móviles y PC. Cada una de las plataformas o dispositivos usados por el cliente crea una nueva experiencia potencial para el cliente. Agregar una experiencia móvil que amplíe la solución principal es la forma más rápida de mejorar la integración en el entorno inmediato del cliente. Aunque un dispositivo móvil esté lejos del ambiente, podría estar más próximo a la necesidad del cliente.

Cuando los clientes cambian de ubicación con frecuencia, puede ser la forma más pertinente de experiencia ambiental para una solución determinada. Una fuente común de innovación en la última década ha sido la expansión de las soluciones existentes para integrar una experiencia móvil.

Algunos ejemplos de este enfoque se pueden ver en Azure App Services. Durante las primeras iteraciones, se puede usar la [característica de aplicación web de Azure App Service](/azure/app-service/overview) para probar la hipótesis. A medida que las hipótesis se vuelven más complejas, la [característica de aplicación móvil de Azure App Services](/azure/app-service-mobile/) puede ampliar la aplicación web para que se ejecute en diversas plataformas móviles.

## <a name="mixed-reality"></a>Realidad mixta

El siguiente nivel de madurez para las experiencias ambientales es el aumento o la replicación del entorno del cliente mediante soluciones de realidad mixta. En este enfoque, la solución se vuelve más ambiental al crear una extensión de realidad para que el cliente opere dentro.

> [!IMPORTANT]
> Si se requiere un dispositivo de realidad virtual y *todavía no forma parte de los comportamientos naturales o circundantes inmediatos*, la realidad virtual o aumentada es más una experiencia alternativa y menos una experiencia ambiental.

Esta forma de experiencia es cada vez más común para los empleados remotos. El uso de estas experiencias está creciendo aún más rápido en sectores que requieren conocimientos de colaboración o especializados que no están disponibles en el mercado local. Un escenario común que requiere una realidad aumentada como parte de un comportamiento natural es la implementación centralizada de un producto complejo para una tarea de trabajo remoto. En estos casos, el equipo de soporte técnico central y el empleado remoto pueden aprovechar la realidad aumentada para solucionar problemas o instalar el producto.

En el escenario anterior o en otros similares, un ejemplo de una experiencia ambiental sería el uso de anclajes espaciales. Los anclajes espaciales le permiten crear experiencias de realidad mixta con objetos cuya ubicación persiste en todos los dispositivos a lo largo del tiempo. Los anclajes espaciales se usan para capturar, grabar y conservar un comportamiento específico, que proporcionará una experiencia ambiental la próxima vez que el usuario opere dentro de ese entorno aumentado. [Azure Spatial Anchors](https://docs.microsoft.com/azure/spatial-anchors/overview) es un servicio que pasa esta lógica a la nube, lo que permite compartir experiencias entre dispositivos e incluso entre soluciones.

## <a name="integrated-reality"></a>Realidad integrada

La realidad integrada va más allá de la realidad móvil o incluso de la realidad mixta. En este enfoque, el objetivo es eliminar por completo la experiencia digital. Todos los dispositivos que usamos tienen funcionalidades de conectividad y proceso. Estos dispositivos se pueden usar para recopilar datos del entorno inmediato sin que el cliente tenga que tocar un teléfono, un portátil o un dispositivo de realidad virtual.

Esta forma de experiencia es ideal cuando una forma de dispositivo es coherente en el mismo entorno en el que se produce la necesidad del cliente. Entre los escenarios comunes se incluyen las plantas fabriles, los ascensores o incluso su automóvil. Estos tipos de dispositivos grandes ya contienen potencia de proceso. También puede usar datos del propio dispositivo para detectar los comportamientos del cliente y enviarlos a la nube. Esta captura automática de los datos de comportamiento del cliente reduce drásticamente la necesidad de que un cliente escriba datos. Además, la experiencia web, móvil o de realidad virtual se puede usar como un bucle de comentarios para compartir lo que se ha aprendido de la solución de realidad integrada.

Entre los ejemplos de realidad integrada en Azure se incluyen:

- [Soluciones de Internet de las cosas (IoT) de Azure](https://docs.microsoft.com/azure/iot-fundamentals), una colección de servicios de Azure que ayudan a administrar los dispositivos y el flujo de datos desde esos dispositivos hacia la nube y de vuelta a los usuarios finales.
- [Azure Sphere](/azure-sphere) es una combinación de hardware y software que, de manera intrínsecamente segura, permite la transmisión de datos entre el dispositivo y las soluciones de Azure IoT.
- El [kit para desarrolladores de Azure Kinect](https://docs.microsoft.com/azure/Kinect-dk), sensores de IA con modelos avanzados de visión y voz, que pueden recopilar datos visuales y de audio del entorno inmediato y alimentar dichas entradas en la solución.

Los tres se pueden usar para recopilar datos dentro del entorno natural, en el punto de necesidad del cliente. A partir de ahí, la solución puede responder a esas entradas de datos para resolver la necesidad, a veces antes de que el cliente sea consciente de que se ha desencadenado esa necesidad.

## <a name="adjusted-reality"></a>Realidad ajustada

La forma más refinada de experiencia ambiental es la realidad ajustada, también conocida como inteligencia ambiental. La realidad ajustada es un enfoque para usar la información de la solución para cambiar la realidad del cliente, sin necesidad de interactuar directamente con una aplicación. En este enfoque, la aplicación que creó inicialmente para demostrar su hipótesis puede que ya no sea pertinente. En su lugar, los dispositivos del entorno facilitarían las entradas y salidas para satisfacer las necesidades de los clientes.

Los asistentes virtuales o altavoces inteligentes son un buen ejemplo de realidad ajustada. Por sí mismo, un altavoz inteligente es un ejemplo de realidad integrada simple. Agregue una luz inteligente y un sensor de movimiento a una solución de altavoz inteligente, y habrá creado fácilmente una solución básica que encienda las luces cuando se entra en una habitación.

Las fábricas de todo el mundo son otros escenarios de realidad ajustada. En las primeras fases de la realidad integrada, los sensores de los dispositivos detectaban las condiciones, como un sobrecalentamiento, y notificaban la necesidad de cambiar a un humano mediante una aplicación. En la realidad ajustada, el cliente todavía puede implicarse, pero el bucle de comentarios es más estricto. En una fábrica con realidad ajustada, un dispositivo detectaría el sobrecalentamiento en una máquina vital en alguna parte dentro de la línea de montaje. En cualquier otra parte de la planta, un segundo dispositivo ralentizaría la producción ligeramente para permitir que la máquina se enfriara y el ritmo se reanudara cuando se resolviera la condición. En este escenario, el cliente es un participante de segunda mano. El cliente utiliza la aplicación para establecer las reglas y entender cómo han afectado a la producción, pero no sería una parte necesaria del bucle de comentarios.

Los servicios de Azure de la sección anterior, [las soluciones de Internet de las cosas (IoT) de Azure](https://docs.microsoft.com/azure/iot-fundamentals), [Azure Sphere](/azure-sphere) y el [kit para desarrolladores de Azure Kinect](https://docs.microsoft.com/azure/Kinect-dk) podrían ser componentes de una solución de realidad ajustada. La aplicación original y la lógica de negocios serviría como intermediario entre la entrada del entorno y el cambio que se debe realizar en el entorno físico.

Otro ejemplo de realidad ajustada es la creación de un gemelo digital, que es una representación digital de un dispositivo físico, presentado con formato de equipo, dispositivo móvil o realidad mixta. A diferencia de los modelos 3D menos sofisticados, un gemelo digital refleja los datos recopilados de un dispositivo real en el entorno físico. Esto permite al usuario interactuar con la representación digital de maneras que nunca podrían darse en el mundo real. En este enfoque, los dispositivos físicos ajustan un entorno de realidad mixta. Sin embargo, la solución sigue recopilando datos de una solución de realidad integrada y usándolos para dar forma a la realidad del entorno actual del cliente.

En Azure, se crean gemelos digitales y se accede a ellos con un servicio llamado [Azure Digital Twins](https://docs.microsoft.com/azure/digital-twins/about-digital-twins).

## <a name="next-steps"></a>Pasos siguientes

Ahora que conoce mejor las interacciones con los dispositivos y la experiencia ambiental adecuada para su solución, ya está preparado para explorar la materia final de innovación: [predicción e influencia](./predict.md).

> [!div class="nextstepaction"]
> [Predicción e influencia](./predict.md)
