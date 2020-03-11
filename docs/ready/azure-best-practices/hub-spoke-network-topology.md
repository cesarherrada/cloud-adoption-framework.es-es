---
title: Topología de red en estrella tipo hub-and-spoke
description: Obtenga información sobre las topologías de red en estrella tipo hub-and-spoke.
author: tracsman
ms.author: jonor
ms.date: 05/10/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: ready
manager: rossort
tags: azure-resource-manager
ms.custom: virtual-network
ms.openlocfilehash: a8ff3977f7a5935dffb0e3bdc013e8730b4c1ff2
ms.sourcegitcommit: 58ea417a7df3318e3d1a76d3807cc4e7e3976f52
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2020
ms.locfileid: "78891927"
---
<!-- cSpell:ignore tracsman jonor rossort NVAs -->

# <a name="hub-and-spoke-network-topology"></a>Topología de red en estrella tipo hub-and-spoke

La red de *concentrador y radio* es un modelo de redes que permite la administración eficaz de los requisitos habituales de comunicación o seguridad. También ayuda a evitar las limitaciones de las suscripciones de Azure. Este modelo aborda los siguientes aspectos:

- **Ahorro en costos y eficiencia de la administración**. La centralización de los servicios que se pueden compartir entre varias cargas de trabajo, como las aplicaciones virtuales de red (NVA) y los servidores DNS, en una única ubicación permite que TI minimice los recursos redundantes y el esfuerzo de administración.
- **Superación de los límites de las suscripciones**. Las cargas de trabajo grandes basadas en la nube pueden requerir el uso de más recursos que los permitidos en una sola suscripción de Azure. El emparejamiento de redes virtuales de carga de trabajo de distintas suscripciones con un centro de conectividad central puede superar estos límites. Para más información, consulte [Límites de suscripción](https://docs.microsoft.com/azure/azure-subscription-service-limits).
- **Separación de cuestiones**. Puede implementar cargas de trabajo individuales entre los equipos de TI centrales y los equipos de las cargas de trabajo.

Es posible que los entornos en la nube más pequeños no se beneficien de la estructura y las funcionalidades agregadas que ofrece este modelo. Pero los trabajos de adopción de la nube mayores deben considerar la implementación de una arquitectura de red en estrella tipo hub-and-spoke si tienen alguna de las preocupaciones mencionadas anteriormente.

> [!NOTE]
> El sitio de arquitecturas de referencia de Azure contiene plantillas de ejemplo que puede usar como base para implementar sus propias redes en estrella tipo hub-and-spoke:
>
> - [Implementación de una topología de red en estrella tipo hub-and-spoke en Azure](https://docs.microsoft.com/azure/architecture/reference-architectures/hybrid-networking/hub-spoke)
> - [Implementación de una topología de red en estrella tipo hub-and-spoke con servicios compartidos en Azure](https://docs.microsoft.com/azure/architecture/reference-architectures/hybrid-networking/shared-services)

## <a name="overview"></a>Información general

![Ejemplos de una topología en estrella tipo hub-and-spoke][1]

Como se muestra en el diagrama, Azure admite dos tipos de diseño en estrella tipo hub-and-spoke. Admite la comunicación, los recursos compartidos y la directiva de seguridad centralizada ("concentrador de VNet" en el diagrama) o un tipo de WAN virtual ("WAN virtual" en el diagrama) para comunicaciones de rama a rama y de rama a Azure a gran escala.

Un concentrador es la zona de red central que controla e inspecciona el tráfico de entrada y salida entre las diferentes zonas: Internet, local y radial. La topología en estrella tipo hub-and-spoke ofrece al departamento de TI una manera eficaz de aplicar directivas de seguridad en una ubicación central. También reduce la posibilidad de exposición y de configuración incorrecta.

El concentrador contiene los componentes de los servicios comunes utilizados por los radios. Los ejemplos siguientes son servicios centrales comunes:

- La infraestructura de Windows Server Active Directory necesaria para la autenticación de usuarios de terceros que acceden desde redes que no son de confianza antes de obtener acceso a las cargas de trabajo del radio. Incluye los Servicios de federación de Active Directory (AD FS) relacionados.
- Un servicio DNS que resuelve los nombres de la carga de trabajo en los radios para acceder a recursos locales y en Internet si no se utiliza [Azure DNS](https://docs.microsoft.com/azure/dns/dns-overview).
- Una infraestructura de clave pública (PKI), para implementar el inicio de sesión único en las cargas de trabajo.
- Control de flujo de tráfico TCP y UDP entre las zonas de red de los radios (spokes) e Internet.
- Control de flujo entre los radios (spokes) y local.
- Si es necesario, control de flujo entre un radio y otro.

Puede minimizar la redundancia, simplificar la administración y reducir el costo general mediante el uso de la infraestructura de concentrador compartida para admitir varios radios.

El rol de cada radio puede ser el hospedaje de diferentes tipos de cargas de trabajo. Los radios (spokes) también proporcionan un enfoque modular para implementaciones repetibles de las mismas cargas de trabajo. Algunos ejemplos son desarrollo y pruebas, pruebas de aceptación del usuario, ensayo y producción.

Los radios también pueden segregar y habilitar varios grupos dentro de su organización. Por ejemplo, los grupos de Azure DevOps. Dentro de un radio, es posible implementar una carga de trabajo básica o cargas de trabajo de varios niveles complejas con control de tráfico entre los niveles.

## <a name="subscription-limits-and-multiple-hubs"></a>Límites de la suscripción y múltiples concentradores

En Azure, todos los componentes, de cualquier tipo, se implementan en una suscripción de Azure. El aislamiento de componentes de Azure en distintas suscripciones de Azure puede satisfacer los requisitos de diferentes líneas de negocio, como la configuración de niveles diferenciados de acceso y autorización.

Una única implementación en estrella tipo hub-and-spoke puede escalarse verticalmente a un gran número de radios. Pero, al igual que pasa con todos los sistemas de TI, hay límites en las plataformas. La implementación del centro se enlaza a una suscripción de Azure específica que tiene restricciones y límites. Un ejemplo es un número máximo de emparejamientos de redes virtuales. Para más información, consulte [Límites, cuotas y restricciones de suscripción y servicios de Microsoft Azure](https://docs.microsoft.com/azure/azure-subscription-service-limits).

En los casos en los que los límites puedan ser un problema, puede escalar verticalmente la arquitectura extendiendo el modelo desde un único concentrador y radio a un clúster de concentradores y radios. Puede conectar entre sí varios concentradores en una o más regiones de Azure mediante el emparejamiento de redes virtuales, Azure ExpressRoute, una WAN virtual o una red privada virtual de sitio a sitio.

![Clúster de concentradores y radios][2]

La introducción de varios concentradores aumenta la sobrecarga del costo y del esfuerzo del sistema. Esto solo se justifica por motivos de escalabilidad, límites del sistema o redundancia y replicación regional para el rendimiento del usuario o recuperación ante desastres. En escenarios que requieran múltiples concentradores, todos los concentradores deben procurar ofrecer el mismo conjunto de servicios para facilitar la operativa.

## <a name="interconnection-between-spokes"></a>Interconexión entre los radios

Es posible implementar cargas de trabajo complejas de varios niveles en un único radio. Puede implementar configuraciones de varios niveles mediante el uso de subredes (una para cada nivel) en la misma red virtual y el uso de grupos de seguridad de red para filtrar los flujos.

Un arquitecto podría querer implementar una carga de trabajo de varios niveles entre varias redes virtuales. Con el emparejamiento de redes virtuales, los radios pueden conectarse a otros radios en el mismo concentrador o en concentradores diferentes.

Un ejemplo típico de este escenario es el caso en el que los servidores de procesamiento de la aplicación están en un radio o red virtual. La base de datos se implementa en un radio o red virtual diferente. En este caso, es fácil interconectar los radios con el emparejamiento de redes virtuales y así evitar el tránsito a través del concentrador. La solución consiste en realizar una revisión cuidadosa de la arquitectura y la seguridad para asegurarse de que evitar el paso por el concentrador no omite puntos de seguridad o auditoría de importancia que podrían existir solo en el concentrador.

![Radios que se conectan entre sí y un concentrador][3]

Los radios también pueden estar conectados entre sí mediante un radio que actúa como concentrador. Este método crea una jerarquía de dos niveles: el radio del nivel superior (nivel 0) se convierten en el concentrador de radios inferiores (nivel 1) en la jerarquía. Los radios de una implementación en estrella tipo hub-and-spoke están obligados a reenviar el tráfico al centro principal, con el fin de que pueda llegar a su destino pasando por la red local o Internet pública. Una arquitectura con dos niveles de concentradores presenta un enrutamiento complejo que anula las ventajas de una relación en estrella tipo hub-and-spoke simple.

<!-- images -->

[1]: ../../_images/azure-best-practices/network-hub-spoke-high-level.png "Ejemplo de alto nivel de una red de concentrador y radio"
[2]: ../../_images/azure-best-practices/network-hub-spokes-cluster.png "Clúster de concentradores y radios"
[3]: ../../_images/azure-best-practices/network-spoke-to-spoke.png "Radio a radio"
