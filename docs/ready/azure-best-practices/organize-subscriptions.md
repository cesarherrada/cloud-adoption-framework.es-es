---
title: Organización y administración de varias suscripciones de Azure
description: Use Cloud Adoption Framework para Azure para más información sobre la creación de una jerarquía de grupos de administración para simplificar la administración de suscripciones y recursos.
author: alexbuckgit
ms.author: abuck
ms.date: 05/20/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: ready
ms.openlocfilehash: e874c518537232104d9bbddbdf8e84841239e56b
ms.sourcegitcommit: ea63be7fa94a75335223bd84d065ad3ea1d54fdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80359869"
---
# <a name="organize-and-manage-multiple-azure-subscriptions"></a>Organización y administración de varias suscripciones de Azure

Si solo tiene algunas suscripciones, administrarlas de forma independiente es relativamente sencillo. Pero si tiene muchas suscripciones, cree una jerarquía de grupos de administración que le ayude a administrar las suscripciones y recursos.

## <a name="azure-management-groups"></a>Grupos de administración de Azure

Los grupos de administración de Azure permiten una administración eficaz del acceso, las directivas y el cumplimiento de las suscripciones de una organización. Cada grupo de administración es un contenedor de una o más suscripciones.

Los grupos de administración están organizados en una sola jerarquía. Esta jerarquía se define en el inquilino de Azure Active Directory (Azure AD) para que se alinee con la estructura y las necesidades de la organización. El nivel superior se denomina *grupo de administración raíz*. Puede definir hasta seis niveles de grupos de administración en la jerarquía. Cada suscripción está contenida en un solo grupo de administración.

Azure proporciona cuatro niveles de ámbito de administración:

- Grupos de administración
- Suscripciones
- Grupos de recursos
- Recursos

Cualquier acceso o directiva aplicados en un nivel de la jerarquía se hereda por los niveles inferiores. El propietario de un recurso o de una suscripción no puede modificar una directiva heredada. Esta limitación ayuda a mejorar la gobernanza.

> [!NOTE]
> La herencia de etiquetas no se admite en este momento, pero lo hará próximamente.

Este modelo de herencia le permite organizar las suscripciones de la jerarquía de forma que cada suscripción siga las directivas y los controles de seguridad adecuados.

![Los cuatro niveles de ámbito para organizar los recursos de Azure](../../ready/azure-setup-guide/media/organize-resources/scope-levels.png)

Todas las asignaciones de acceso o directivas en el grupo de administración raíz se aplican a todos los recursos dentro del directorio. Considere cuidadosamente qué elementos define en este ámbito. Incluya solo las asignaciones que debe tener.

## <a name="create-your-management-group-hierarchy"></a>Creación de la jerarquía de grupos de administración

Al definir la jerarquía de grupos de administración, primero debe crear el grupo de administración raíz. A continuación, mueva todas las suscripciones existentes en el directorio al grupo de administración raíz. Las nuevas suscripciones siempre se crean en el grupo de administración raíz. Posteriormente, puede moverlas a otro grupo de administración.

Cuando se mueve una suscripción a un grupo de administración existente, se heredan las asignaciones de directivas y roles de la jerarquía de grupos de administración que se encuentra por encima. Una vez que haya establecido varias suscripciones para las cargas de trabajo de Azure, puede crear suscripciones adicionales para que contengan los servicios de Azure que otras suscripciones comparten.

Si prevé que el entorno de Azure crecerá, debe crear grupos de administración de producción y de no producción ahora, y aplicar las directivas y controles de acceso adecuados en el nivel del grupo de administración. Las nuevas suscripciones heredarán los controles adecuados a medida que se agreguen a cada grupo de administración.

![Ejemplo de una jerarquía de grupos de administración](../../_images/ready/management-group-hierarchy-v2.png)

## <a name="example-use-cases"></a>Casos de uso de ejemplo

Estos son algunos ejemplos básicos del uso de grupos de administración para separar diferentes cargas de trabajo:

- **Cargas de trabajo de producción y de no producción:** Use los grupos de administración para administrar más fácilmente los distintos roles y directivas entre las suscripciones de producción y de no producción. Por ejemplo, en las suscripciones que no son de producción se puede conceder a los desarrolladores acceso de "colaborador", mientras que en las de producción solo tendrán acceso de "lector".
- **Servicios internos frente a servicios externos:** Las empresas suelen tener requisitos, directivas y roles diferentes para los servicios internos y los servicios externos orientados al cliente.

## <a name="related-resources"></a>Recursos relacionados

Revise los siguientes recursos para más información sobre la organización y administración de los recursos de Azure.

- [Organización de los recursos con grupos de administración de Azure](https://docs.microsoft.com/azure/governance/management-groups)
- [Elevación de los privilegios de acceso para administrar todas las suscripciones y los grupos de administración de Azure](https://docs.microsoft.com/azure/role-based-access-control/elevate-access-global-admin)
- [Traslado de recursos de Azure a otro grupo de recursos o a otra suscripción](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-move-resources)

## <a name="next-steps"></a>Pasos siguientes

Revise las [convenciones de recomendadas de nomenclatura y etiquetado](./naming-and-tagging.md) que se deben seguir al implementar los recursos de Azure.

> [!div class="nextstepaction"]
> [Convenciones recomendadas de nomenclatura y etiquetado](./naming-and-tagging.md)
