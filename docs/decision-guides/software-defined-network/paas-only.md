---
title: 'Red definida por software: solo PaaS'
description: Explicación del modelo solo PaaS para redes definidas por software en la nube.
author: rotycenh
ms.author: v-tyhopk
ms.date: 02/11/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: decision-guide
ms.custom: governance
ms.openlocfilehash: d61c9562b34453e6a0026a15a2674e3e19854810
ms.sourcegitcommit: 2362fb3154a91aa421224ffdb2cc632d982b129b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76804833"
---
# <a name="software-defined-networking-paas-only"></a>Red definida por software: solo PaaS

Al implementar un recurso de plataforma como servicio (PaaS), el proceso de implementación crea automáticamente una red asumida subyacente con un número limitado de controles a través de dicha red, como equilibrio de carga, bloqueo de puertos y conexiones a otros servicios PaaS.

En Azure, varios tipos de recursos PaaS se pueden [implementar](https://docs.microsoft.com/azure/virtual-network/virtual-network-for-azure-services) en una red virtual o [conectarse](https://docs.microsoft.com/azure/virtual-network/virtual-network-service-endpoints-overview) a ella, permitiendo que estos recursos se integren en la infraestructura de red virtual existente. Otros servicios, como [App Service Environment](https://docs.microsoft.com/azure/app-service/environment/intro), [Azure Kubernetes Service (AKS)](https://docs.microsoft.com/azure/aks/intro-kubernetes) y [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) deben implementarse dentro de la red virtual. Pero, en muchos casos, para cumplir los requisitos de conectividad y administración de tráfico de una carga de trabajo, basta con tener una arquitectura de red solo PaaS, basada exclusivamente en las capacidades de red nativas predeterminadas proporcionadas por los recursos PaaS.

Si se plantea la opción de usar una arquitectura de red solo PaaS, asegúrese de validar que las suposiciones necesarias están en consonancia con los requisitos.

## <a name="paas-only-assumptions"></a>Suposiciones solo PaaS

Para la implementación de una arquitectura de red solo PaaS, se supone lo siguiente:

- La aplicación que se va a implementar es una aplicación independiente o solamente depende de otros recursos PaaS que no necesitan una red virtual.
- Los equipos de operaciones de TI pueden actualizar sus herramientas, formación y procesos para admitir la administración, configuración e implementación de aplicaciones PaaS independientes.
- La aplicación PaaS no forma parte de un trabajo de migración a nube más amplio que incluirá recursos IaaS.

Estas suposiciones son calificadores mínimos alineados con la implementación de una red solo PaaS. Aunque este enfoque puede estar en consonancia con los requisitos de una implementación de una sola aplicación, cada equipo de adopción de la nube debería tener en cuenta estas preguntas a largo plazo:

- ¿Se ampliará el ámbito o la escala de esta implementación para requerir acceso a otros recursos no PaaS?
- ¿Se han planeado otras implementaciones PaaS más allá de la solución actual?
- ¿La organización tiene planes de realizar otras migraciones a nube futuras?

Las respuestas a estas preguntas no impedirían que un equipo elija una opción solo PaaS, pero deben tenerse en cuenta antes de tomar una decisión definitiva.
