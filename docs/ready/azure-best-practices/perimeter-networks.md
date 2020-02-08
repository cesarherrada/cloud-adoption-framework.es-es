---
title: Redes perimetrales
description: Obtenga más información sobre cómo las redes perimetrales, también conocidas como subredes filtradas (DMZ), usan las características y los servicios de Azure.
author: tracsman
ms.author: jonor
ms.date: 05/10/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: ready
manager: rossort
tags: azure-resource-manager
ms.custom: virtual-network
ms.openlocfilehash: 2aa561a7ffdcf43ffc56ad89849e933ea8abf186
ms.sourcegitcommit: 4948a5f458725e8a0c7206f08502422965a549d5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "76994215"
---
# <a name="perimeter-networks"></a>Redes perimetrales

Las [redes perimetrales][perimeter-network] permiten la conectividad segura entre las redes de la nube y las redes de los centros de datos locales o físicos, así como todo tipo de conectividad hacia Internet y desde este. También se conocen como zonas desmilitarizadas (DMZ).

Para que las redes perimetrales sean eficaces, los paquetes entrantes deben fluir a través de los dispositivos de seguridad hospedados en subredes seguras antes de llegar a los servidores back-end. Algunos ejemplos son el firewall, los sistemas de detección de intrusiones (IDS) y los sistemas de prevención de intrusiones (IPS). Antes de abandonar la red, los paquetes enlazados a Internet de las cargas de trabajo también deberían fluir por las aplicaciones de seguridad de la red perimetral. Este flujo tiene fines de auditoría, inspección y aplicación de directivas.

Las redes perimetrales usan las siguientes características y servicios de Azure:

- [Redes virtuales][virtual-networks], [rutas definidas por el usuario][user-defined-routes] y [grupos de seguridad de red][network-security-groups]
- [Aplicaciones virtuales de red (NVA)][NVA]
- [Equilibrador de carga de Azure][ALB]
- [Azure Application Gateway][AppGW] y [firewall de aplicaciones web (WAF)][AppGWWAF]
- [Direcciones IP públicas][PIP].
- [Azure Front Door][AFD] con [firewall de aplicaciones web][AFDWAF]
- [Azure Firewall][AzFW]

> [!NOTE]
> Las arquitecturas de referencia de Azure proporcionan plantillas de ejemplo que puede usar para implementar sus propias redes perimetrales:
>
> - [Implementación de una zona DMZ entre Azure y el centro de datos local](https://docs.microsoft.com/azure/architecture/reference-architectures/dmz/secure-vnet-hybrid)
> - [Implementación de una zona DMZ entre Azure e Internet](https://docs.microsoft.com/azure/architecture/reference-architectures/dmz/secure-vnet-dmz?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json)

Normalmente, los equipos de TI y de seguridad centrales son responsables de definir los requisitos para el funcionamiento de las redes perimetrales.

![Ejemplo de una topología en estrella tipo hub-and-spoke][7]

En el diagrama anterior se muestra un ejemplo de [topología de red en estrella tipo hub-and-spoke](./hub-spoke-network-topology.md) que implementa la aplicación de dos perímetros con acceso a Internet y a una red local. Ambos perímetros residen en el concentrador de la red perimetral. En el concentrador de DMZ, la red perimetral a Internet puede escalarse verticalmente para admitir varias líneas de negocio mediante varias granjas de firewalls de aplicaciones web que ayudan a proteger las redes virtuales radiales. El concentrador también permite la conectividad a través de VPN o Azure ExpressRoute, según sea necesario.

## <a name="virtual-networks"></a>Redes virtuales

Las redes perimetrales normalmente se basan en una [red virtual][virtual-networks] con varias subredes para hospedar los distintos tipos de servicios con filtrado e inspección del tráfico hacia o desde Internet mediante NVA, WAF e instancias de Azure Application Gateway.

## <a name="user-defined-routes"></a>Rutas definidas por el usuario

Con las [rutas definidas por el usuario][user-defined-routes], los clientes pueden implementar firewalls, IDS o IPS y otras aplicaciones virtuales. Los clientes pueden entonces enrutar el tráfico de red a través de estas aplicaciones de seguridad para la aplicación de directivas de límites de seguridad, auditoría e inspección. Se pueden crear rutas definidas por el usuario para garantizar que el tráfico pase por las máquinas virtuales personalizadas, NVA y equilibradores de carga especificados.

En un ejemplo de red en estrella tipo hub-and-spoke, garantizar que el tráfico generado por las máquinas virtuales que residen en el radio pase a través de los dispositivos virtuales correctos en el concentrador requiere una ruta definida por el usuario definida en las subredes del radio. Esta ruta establece la dirección IP de front-end del equilibrador de carga interno como el tipo de próximo salto. El equilibrador de carga interno distribuye el tráfico interno a las aplicaciones virtuales (grupo de back-end de equilibradores de carga).

## <a name="azure-firewall"></a>Azure Firewall

[Azure Firewall][AzFW] es un servicio administrado basado en red que ayuda a proteger los recursos de la red virtual de Azure. Se trata de un firewall administrado con estado completo, con alta disponibilidad integrada y una escalabilidad sin restricciones en la nube. Puede crear, aplicar y registrar directivas de aplicaciones y de conectividad de red a nivel central en suscripciones y redes virtuales.

Azure Firewall usa una dirección IP pública estática para los recursos de red virtual. Esto permite que los firewalls externos identifiquen el tráfico que procede de su red virtual. El servicio interopera con Azure Monitor para los registros y análisis.

## <a name="network-virtual-appliances"></a>Aplicaciones virtuales de red

Las redes perimetrales con acceso a Internet se administran normalmente mediante una instancia de Azure Firewall o una granja de firewalls o mediante un [firewall de aplicaciones web][AFDWAF].

Las diferentes líneas de negocio normalmente utilizan muchas aplicaciones web. Estas aplicaciones tienden a sufrir varias vulnerabilidades y posibles puntos débiles. Los firewall de aplicaciones web detectan ataques contra las aplicaciones web (HTTP/HTTPS) con mayor profundidad que un firewall genérico. En comparación con la tecnología de firewall tradicional, los firewalls de aplicaciones web tienen un conjunto de características específicas para ayudar a proteger los servidores web internos frente a amenazas.

Una instancia de Azure Firewall y una [aplicación virtual de red firewall][NVA] utiliza un plan de administración común, con un conjunto de reglas de seguridad para proteger las cargas de trabajo hospedadas en los radios y controlar el acceso a las redes locales. Azure Firewall tiene escalabilidad integrada, mientras que los firewalls de aplicación virtual de red se pueden escalar manualmente detrás de un equilibrador de carga.

En general, una granja de firewalls tiene menos software especializado en comparación con un WAF, pero tiene un ámbito más amplio de aplicación para filtrar e inspeccionar cualquier tipo de tráfico de entrada y salida. Si usa un enfoque NVA, puede buscar e implementar el software desde Azure Marketplace.

Use un conjunto de instancias de Azure Firewall (o NVA) para el tráfico que se origina en Internet y otro para el que se origina en el entorno local. Utilizar únicamente un conjunto de firewalls para ambos es un riesgo de seguridad, ya que no proporciona ningún perímetro de seguridad entre los dos conjuntos de tráfico de red. El uso de capas de firewalls independientes reduce la complejidad de la comprobación de las reglas de seguridad y deja claro qué reglas se corresponden con cada solicitud de red entrante.

## <a name="azure-load-balancer"></a>Azure Load Balancer

[Azure Load Balancer][ALB] ofrece un servicio de nivel 4 (TCP y UDP) de alta disponibilidad que puede distribuir el tráfico entrante entre instancias del servicio definidas en un conjunto de equilibrio de carga. El tráfico enviado al equilibrador de carga desde los puntos de conexión front-end (puntos de conexión de direcciones IP públicas o privadas) se puede redistribuir con o sin traducción de direcciones a un grupo de direcciones IP de back-end (ejemplo: aplicaciones virtuales de red o máquinas virtuales).

Azure Load Balancer también puede sondear el estado de las distintas instancias de servidor. Cuando una instancia no puede responder a un sondeo, el equilibrador de carga deja de enviar tráfico a las instancias incorrectas.

Como ejemplo del uso de una topología de red en estrella tipo hub-and-spoke, puede implementar un equilibrador de carga externo en el concentrador y en los radios. En el concentrador, el equilibrador de carga enruta de forma eficaz el tráfico a los servicios de los radios. En los radios, los equilibradores de carga administran el tráfico de la aplicación.

## <a name="azure-front-door-service"></a>Azure Front Door Service

[Azure Front Door Service][AFD] es la plataforma de aceleración de aplicaciones web altamente disponible y escalable de Microsoft y el equilibrador de carga HTTP global. Puede usar Azure Front Door Service para crear, operar y escalar horizontalmente las aplicaciones web dinámicas y el contenido estático. Se ejecuta en más de 100 ubicaciones de la red global de Microsoft.

Azure Front Door Service proporciona a la aplicación una automatización de mantenimiento de marca o regional unificada, una automatización de BCDR, una información de cliente o usuario unificada, un almacenamiento en caché y una información detallada de servicios. La plataforma ofrece Acuerdos de Nivel de Servicio de rendimiento, confiabilidad y soporte técnico. También ofrece certificaciones de cumplimiento y procedimientos de seguridad auditables desarrollados y operados por Azure, y compatibles de forma nativa con Azure.

## <a name="application-gateway"></a>Application Gateway

[Azure Application Gateway][AppGW] es una aplicación virtual dedicada que proporciona un controlador de entrega de aplicaciones (ADC) administrado como servicio. Ofrece diversas funcionalidades de equilibrio de carga de nivel 7 para la aplicación.

Application Gateway permite optimizar la productividad de las granjas de servidores web traspasando la carga de la terminación SSL con mayor actividad de la CPU a la puerta de enlace de aplicaciones. También dispone de otras funcionalidades de enrutamiento de nivel 7, como la distribución round robin del tráfico entrante, la afinidad de sesiones basada en cookies, el enrutamiento basado en rutas de acceso URL y la capacidad de hospedar varios sitios web detrás de una única puerta de enlace de aplicaciones.

El SKU de WAF de la puerta de enlace de aplicaciones cuenta con un firewall de aplicaciones web. Esta SKU proporciona protección a las aplicaciones web frente a vulnerabilidades web y vulnerabilidades de seguridad comunes. Puede configurar Application Gateway como una puerta de enlace accesible desde Internet, una puerta de enlace solo para uso interno o una combinación de las dos.

## <a name="public-ips"></a>Direcciones IP públicas

Algunas características de Azure le permiten asociar los puntos de conexión de servicio a una dirección [IP pública][PIP] que permite al recurso estar accesible desde Internet. Este punto de conexión usa la traducción de direcciones de red (NAT) para enrutar el tráfico a la dirección interna y el puerto de la red virtual de Azure. Esta ruta es la vía principal para que el tráfico externo pase a la red virtual. Las direcciones IP públicas se pueden configurar para determinar qué tráfico se pasa y cómo y a dónde se traslada en la red virtual.

## <a name="azure-ddos-protection-standard"></a>Protección contra DDoS de Azure estándar

[Azure DDoS Protection estándar][DDoS] ofrece funcionalidades adicionales de mitigación en comparación con el nivel de [servicio básico][DDoS], adaptadas específicamente a los recursos de red virtual de Azure. El servicio Protección contra DDoS estándar es fácil de habilitar y no requiere ningún cambio en la aplicación.

Puede ajustar las directivas de protección mediante la supervisión del tráfico dedicado y los algoritmos de aprendizaje automático. Las directivas se aplican a direcciones IP públicas asociadas a recursos implementados en redes virtuales. Algunos ejemplos son instancias de Azure Load Balancer, Azure Application Gateway y Azure Service Fabric.

La telemetría en tiempo real está disponible mediante las vistas de Azure Monitor durante un ataque y con fines históricos. Se puede agregar protección en la capa de aplicación mediante el firewall de aplicaciones web de Azure Application Gateway. Se proporciona protección para direcciones IP públicas de Azure IPv4.

<!-- images -->

[0]: ../../_images/azure-best-practices/network-redundant-equipment.png "Ejemplos de superposición de componentes"
[1]: ../../_images/azure-best-practices/network-hub-spoke-high-level.png "Ejemplo de alto nivel de una red de concentrador y radio"
[2]: ../../_images/azure-best-practices/network-hub-spokes-cluster.png "Clúster de concentradores y radios"
[3]: ../../_images/azure-best-practices/network-spoke-to-spoke.png "Radio a radio"
[4]: ../../_images/azure-best-practices/network-hub-spoke-block-level-diagram.png "Diagrama de nivel de bloques del concentrador y radio"
[5]: ../../_images/azure-best-practices/network-users-groups-subscriptions.png "Usuarios, grupos, suscripciones y proyectos"
[6]: ../../_images/azure-best-practices/network-infrastructure-high-level.png "Diagrama de infraestructura de alto nivel"
[7]: ../../_images/azure-best-practices/network-high-level-perimeter-networks.png "Diagrama de infraestructura de alto nivel"
[8]: ../../_images/azure-best-practices/network-vnet-peering-perimeter-networks.png "Emparejamiento de redes virtuales y redes perimetrales"
[9]: ../../_images/azure-best-practices/network-high-level-diagram-monitoring.png "Diagrama de alto nivel para supervisión"
[10]: ../../_images/azure-best-practices/network-high-level-workloads.png "Diagrama de alto nivel para cargas de trabajo"

<!-- links -->

[Limits]: https://docs.microsoft.com/azure/azure-subscription-service-limits
[Roles]: https://docs.microsoft.com/azure/role-based-access-control/built-in-roles
[virtual-networks]: https://docs.microsoft.com/azure/virtual-network/virtual-networks-overview
[network-security-groups]: https://docs.microsoft.com/azure/virtual-network/virtual-networks-nsg
[DNS]: https://docs.microsoft.com/azure/dns/dns-overview
[PrivateDNS]: https://docs.microsoft.com/azure/dns/private-dns-overview
[VNetPeering]: https://docs.microsoft.com/azure/virtual-network/virtual-network-peering-overview
[user-defined-routes]: https://docs.microsoft.com/azure/virtual-network/virtual-networks-udr-overview
[RBAC]: https://docs.microsoft.com/azure/role-based-access-control/overview
[azure-ad]: https://docs.microsoft.com/azure/active-directory/active-directory-whatis
[VPN]: https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpngateways
[ExR]: https://docs.microsoft.com/azure/expressroute/expressroute-introduction
[ExRD]: https://docs.microsoft.com/azure/expressroute/expressroute-erdirect-about
[vWAN]: https://docs.microsoft.com/azure/virtual-wan/virtual-wan-about
[NVA]: https://docs.microsoft.com/azure/architecture/reference-architectures/dmz/nva-ha
[AzFW]: https://docs.microsoft.com/azure/firewall/overview
[SubMgmt]: https://docs.microsoft.com/azure/architecture/cloud-adoption/reference/azure-scaffold
[RGMgmt]: https://docs.microsoft.com/azure/azure-resource-manager/resource-group-overview
[perimeter-network]: https://docs.microsoft.com/azure/best-practices-network-security
[ALB]: https://docs.microsoft.com/azure/load-balancer/load-balancer-overview
[DDoS]: https://docs.microsoft.com/azure/virtual-network/ddos-protection-overview
[PIP]: https://docs.microsoft.com/azure/virtual-network/virtual-network-public-ip-address
[AFD]: https://docs.microsoft.com/azure/frontdoor/front-door-overview
[AFDWAF]: https://docs.microsoft.com/azure/frontdoor/waf-overview
[AppGW]: https://docs.microsoft.com/azure/application-gateway/application-gateway-introduction
[AppGWWAF]: https://docs.microsoft.com/azure/application-gateway/application-gateway-web-application-firewall-overview
[Monitor]: https://docs.microsoft.com/azure/monitoring-and-diagnostics/
[ActLog]: https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-activity-logs
[DiagLog]: https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-of-diagnostic-logs
[nsg-log]: https://docs.microsoft.com/azure/virtual-network/virtual-network-nsg-manage-log
[OMS]: https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview
[NPM]: https://docs.microsoft.com/azure/log-analytics/log-analytics-network-performance-monitor
[NetWatch]: https://docs.microsoft.com/azure/network-watcher/network-watcher-monitoring-overview
[WebApps]: https://docs.microsoft.com/azure/app-service/
[HDI]: https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-introduction
[EventHubs]: https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs
[ServiceBus]: https://docs.microsoft.com/azure/service-bus-messaging/service-bus-messaging-overview
[traffic-manager]: https://docs.microsoft.com/azure/traffic-manager/traffic-manager-overview
