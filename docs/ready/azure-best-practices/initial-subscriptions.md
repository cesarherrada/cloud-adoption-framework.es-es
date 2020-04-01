---
title: Creación de las suscripciones de Azure iniciales
description: Comience el proceso de adopción de Azure mediante la creación de las suscripciones iniciales.
author: alexbuckgit
ms.author: abuck
ms.date: 05/20/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: ready
ms.openlocfilehash: 4e2a538c91328e7153f7f5ed37d07b8dbbeb4ea0
ms.sourcegitcommit: ea63be7fa94a75335223bd84d065ad3ea1d54fdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80359885"
---
# <a name="create-your-initial-azure-subscriptions"></a>Creación de las suscripciones de Azure iniciales

Para empezar el proceso de adopción de Azure, cree un conjunto inicial de suscripciones. Obtenga información sobre las suscripciones con las que debe comenzar según sus requisitos iniciales.

## <a name="your-first-two-subscriptions"></a>Las dos primeras suscripciones

Empiece por crear dos suscripciones:

- Cree una suscripción de Azure para que contenga las cargas de trabajo de producción.
- Cree una segunda suscripción que actúe como entorno de no producción (desarrollo y pruebas), mediante una [oferta con el plan de tarifa Desarrollo/pruebas de Azure](https://azure.microsoft.com/pricing/dev-test) para conseguir un precio más reducido.

![Un modelo de suscripción inicial que muestra imágenes de llaves junto a cuadros de producción y no producción](../../_images/ready/initial-subscription-model.png)

Este enfoque tiene muchas ventajas:

- El uso de suscripciones independientes para los entornos de producción y de no producción crea un límite que hace que la administración de los recursos sea más sencilla y segura.
- Azure tiene ofertas específicas de suscripción de desarrollo y pruebas para las cargas de trabajo que no son de producción. Estas ofertas proporcionan tarifas con descuento para los servicios y licencias de software de Azure.
- Los entornos de producción y no producción probablemente tendrán diferentes conjuntos de directivas de Azure. El uso de suscripciones independientes simplifica la aplicación de cada directiva específica en el nivel de suscripción.
- Puede permitir determinados tipos de recursos de Azure en la suscripción de no producción con fines de prueba. Puede habilitar esos proveedores de recursos en la suscripción de no producción sin que estén disponibles en el entorno de producción.
- Puede usar las suscripciones de desarrollo y pruebas como entornos de espacio aislado. Estos espacios aislados permiten a los administradores y desarrolladores crear y eliminar rápidamente conjuntos completos de recursos de Azure. Este aislamiento también puede ayudar con la protección de datos y los problemas de seguridad.
- Los umbrales de costo aceptables variarán probablemente entre las suscripciones de producción y de desarrollo y pruebas.

## <a name="sandbox-subscriptions"></a>Suscripciones de espacio aislado

Si incluye objetivos de innovación como parte de la estrategia de adopción de la nube, considere la posibilidad de crear una o varias suscripciones de espacio aislado. Puede aplicar directivas de seguridad para mantener estas suscripciones de prueba aisladas de los entornos de producción y de no producción. Los usuarios pueden experimentar fácilmente con las funcionalidades de Azure en estos entornos aislados. Use la oferta del plan de tarifa Desarrollo/pruebas de Azure para crear estas suscripciones.

![Un modelo de suscripción inicial que muestra imágenes de llaves junto a cuadros de producción, no producción y espacios aislados](../../_images/ready/initial-subscription-model-with-sandboxes.png)

## <a name="shared-services-subscription"></a>Suscripción de servicios compartidos

Si planea hospedar **más de 1000 máquinas virtuales o instancias de proceso en la nube en un plazo de 24 meses**, cree otra suscripción de Azure para hospedar servicios compartidos. Esto le preparará por anticipado para poder admitir la arquitectura empresarial en su estado final.

![Un modelo de suscripción inicial que muestra imágenes de llaves junto a cuadros de producción, no producción y servicios compartidos](../../_images/ready/initial-subscription-model-with-shared-services.png)

## <a name="next-steps"></a>Pasos siguientes

Revise las razones por las que es posible que quiera [crear suscripciones de Azure adicionales](./scale-subscriptions.md) para satisfacer sus necesidades.

> [!div class="nextstepaction"]
> [Creación de suscripciones adicionales para escalar el entorno de Azure](./scale-subscriptions.md)
