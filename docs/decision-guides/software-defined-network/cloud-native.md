---
title: 'Red definida por software: Nativo de la nube'
description: Use Cloud Adoption Framework de Azure para más información sobre las redes virtuales nativas en la nube que son necesarias para la implementación de máquinas virtuales en la nube.
author: rotycenh
ms.author: abuck
ms.date: 02/11/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: decision-guide
ms.custom: governance
ms.openlocfilehash: 5fc722b46c860fff1880d864604993bf02c05447
ms.sourcegitcommit: 25cd1b3f218d0644f911737a6d5fd259461b2458
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2020
ms.locfileid: "80225760"
---
# <a name="software-defined-networking-cloud-native"></a>Red definida por software: Nativo de la nube

Se requiere una red virtual nativa en la nube para implementar recursos de IaaS, como las máquinas virtuales, en una plataforma en la nube. El acceso a redes virtuales de orígenes externos, similares a la web, se debe proporcionar explícitamente. Este tipo de redes virtuales admiten la creación de subredes y reglas de enrutamiento, así como firewalls virtuales y dispositivos de administración de tráfico.

Una red virtual nativa en la nube no depende de los recursos locales de la organización ni de otros recursos que no sean de nube para admitir las cargas de trabajo hospedadas en la nube. Todos los recursos necesarios se aprovisionan en la propia red virtual o mediante ofertas PaaS administradas.

## <a name="cloud-native-assumptions"></a>Supuestos de la red virtual nativa en la nube

En la implementación de una red virtual nativa en la nube se da por hecho lo siguiente:

- Las cargas de trabajo que se implementan en la red virtual no dependen de aplicaciones o servicios a los que solo se puede acceder desde dentro de la red local. A menos que proporcionen puntos de conexión accesibles en la red pública de Internet, los recursos hospedados en una plataforma de nube no pueden utilizar las aplicaciones y los servicios hospedados internamente en el entorno local.
- La administración de identidades de la carga de trabajo y el control de acceso dependen de los servicios de identidad de la plataforma de nube o de los servidores IaaS hospedados en su entorno en nube. No necesitará conectarse directamente a los servicios de identidad hospedados en el entorno local o en otras ubicaciones externas.
- Los servicios de identidad no necesitan admitir el inicio de sesión único (SSO) con directorios locales.

Las redes virtuales nativas en la nube no tienen dependencias externas. Esto hace que sean fáciles de implementar y configurar y, como resultado, esta arquitectura es a menudo la mejor opción para experimentos u otras implementaciones más pequeñas, autónomas o de iteración rápida.

Entre los temas adicionales que el equipo de adopción de la nube debe tener en cuenta al hablar de una arquitectura de red virtual nativa en la nube, se incluyen los siguientes:

- Las cargas de trabajo existentes diseñadas para ejecutarse en un centro de datos local pueden necesitar una amplia modificación para aprovechar la funcionalidad basada en la nube, como los servicios de almacenamiento o autenticación.
- Las redes nativas en la nube se administran únicamente con las herramientas de administración de la plataforma de nube lo que, con el tiempo, puede dar lugar a divergencias en la administración y las directivas con respecto a los estándares de TI existentes.

## <a name="next-steps"></a>Pasos siguientes

Para más información sobre las redes virtuales nativas en la nube en Azure, consulte:

- [Red virtual de Azure: Guías de procedimientos](https://docs.microsoft.com/azure/virtual-network/virtual-network-vnet-plan-design-arm). De forma predeterminada las redes virtuales de Azure que se acaban de crear son nativas para la nube. Use estas guías para ayudar a planear el diseño e implementación de las redes virtuales.
- [Límites de suscripción: Redes](https://docs.microsoft.com/azure/azure-subscription-service-limits?toc=/azure/virtual-network/toc.json#networking-limits). Cada red virtual y sus recursos conectados existen en una suscripción única. Estos recursos están limitados por los límites de la suscripción.
