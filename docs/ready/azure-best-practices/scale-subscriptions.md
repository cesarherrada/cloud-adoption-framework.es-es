---
title: Creación de suscripciones adicionales para escalar el entorno de Azure
description: Use Cloud Adoption Framework para Azure para aprender a desarrollar una estrategia de escalado del entorno mediante varias suscripciones de Azure.
author: alexbuckgit
ms.author: abuck
ms.date: 05/20/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: ready
ms.openlocfilehash: dd052e42bc9685701df831878c12ed37ed42395c
ms.sourcegitcommit: ea63be7fa94a75335223bd84d065ad3ea1d54fdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80359865"
---
# <a name="create-additional-subscriptions-to-scale-your-azure-environment"></a>Creación de suscripciones adicionales para escalar el entorno de Azure

Las organizaciones suelen usar varias suscripciones de Azure para evitar límites de recursos por suscripción y administrar y gobernar mejor sus recursos de Azure. Es importante definir una estrategia para escalar las suscripciones.

## <a name="review-fundamental-concepts"></a>Revisión de los conceptos básicos

A medida que expande el entorno de Azure más allá de las [suscripciones iniciales](./initial-subscriptions.md), es importante comprender conceptos de Azure como cuentas, inquilinos, directorios y suscripciones. Para más información, consulte [Conceptos básicos de Azure](../considerations/fundamental-concepts.md).

Otras consideraciones podrían requerir suscripciones adicionales. Tenga en cuenta lo siguiente al ampliar su espacio en la nube.

## <a name="technical-considerations"></a>Consideraciones técnicas

**Límites de suscripción:** Las suscripciones tienen límites definidos para algunos tipos de recursos. Por ejemplo, el número de redes virtuales de una suscripción es limitado. Si una suscripción se acerca a estos límites, tendrá que crear otra suscripción y colocar ahí los recursos adicionales. Para más información, consulte [Azure subscription and service limits](https://docs.microsoft.com/azure/azure-subscription-service-limits#general-limits) (Límites de suscripción y servicio de Azure).

**Recursos del modelo clásico:** Si usa Azure desde hace mucho tiempo, puede que tenga recursos que se crearon con el modelo de implementación clásica. Las directivas de Azure, el control de acceso basado en rol, la agrupación de recursos y las etiquetas no se pueden aplicar a los recursos del modelo clásico. Estos recursos se deben trasladar a suscripciones que contengan solo recursos del modelo clásico.

**Costos:** Es posible que se generen costos adicionales por la entrada y salida de datos entre las suscripciones.

## <a name="business-priorities"></a>Prioridades empresariales

Las prioridades empresariales pueden llevarle a crear suscripciones adicionales. Estas prioridades incluyen:

- Innovación
- Migración
- Coste
- Operaciones
- Seguridad
- Gobernanza

Para otras consideraciones sobre el escalado de las suscripciones, revise la [Guía de decisiones de suscripción](../../decision-guides/subscriptions/index.md) de Cloud Adoption Framework.

## <a name="moving-resources-between-subscriptions"></a>Traslado de recursos entre suscripciones

A medida que crezca el modelo de suscripciones, puede decidir que algunos de los recursos pertenezcan a otras suscripciones. Hay muchos tipos de recursos que se pueden mover entre suscripciones. También puede usar implementaciones automatizadas para volver a crear recursos en otra suscripción. Para más información, consulte [Traslado de los recursos a un nuevo grupo de recursos o a una nueva suscripción](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-move-resources).

## <a name="tips-for-creating-new-subscriptions"></a>Sugerencias para crear suscripciones

- Identifique quién será responsable de crear las suscripciones.
- Decida qué tipos de recursos estarán disponibles en una suscripción de forma predeterminada.
- Decida el aspecto de todas las suscripciones estándar. Es necesario considerar el acceso RBAC, las directivas, las etiquetas y los recursos de infraestructura.
- Si es posible, [cree mediante programación nuevas suscripciones](https://docs.microsoft.com/azure/azure-resource-manager/management/programmatically-create-subscription) con una entidad de servicio. Debe [conceder permiso a la entidad de servicio](https://docs.microsoft.com/azure/azure-resource-manager/grant-access-to-create-subscription) para crear suscripciones. Defina un grupo de seguridad que pueda solicitar nuevas suscripciones a través de un flujo de trabajo automatizado.
- Si es cliente de un Contrato Enterprise (EA), pídale al servicio de soporte técnico de Azure que bloquee la creación de suscripciones no EA en su organización.

## <a name="next-steps"></a>Pasos siguientes

Cree una jerarquía de grupos de administración que le ayude a [organizar y administrar las suscripciones y recursos](./organize-subscriptions.md).

> [!div class="nextstepaction"]
> [Organización y administración de las suscripciones y recursos](./organize-subscriptions.md)
