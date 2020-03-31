---
title: Guía de decisiones de suscripción
description: Comprenda las estrategias de diseño de suscripciones y la jerarquía de grupos de administración para organizar los recursos de Azure.
author: alexbuckgit
ms.author: abuck
ms.date: 10/17/2019
ms.topic: conceptual
ms.service: cloud-adoption-framework
ms.subservice: decision-guide
ms.custom: governance
ms.openlocfilehash: 2f50efb6e73f59affa8c2b463d363644a026b32c
ms.sourcegitcommit: afe10f97fc0e0402a881fdfa55dadebd3aca75ab
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2020
ms.locfileid: "80431175"
---
# <a name="subscription-decision-guide"></a>Guía de decisiones de suscripción

Un diseño eficaz de las suscripciones ayuda a las organizaciones a establecer una estructura para organizar y administrar los recursos de Azure durante un proceso de adopción de la nube. Esta guía le ayudará a decidir cuándo debe crear suscripciones adicionales y expandir la jerarquía de grupos de administración para dar apoyo a sus prioridades empresariales.

## <a name="prerequisites"></a>Prerrequisitos

La adopción de Azure comienza con la creación de una suscripción, la asociación a una cuenta y la implementación de recursos tales como máquinas virtuales y bases de datos en la suscripción. Para una introducción sobre estos conceptos, consulte [Conceptos básicos de Azure](../../ready/considerations/fundamental-concepts.md).

- [Cree las suscripciones iniciales.](../../ready/azure-best-practices/initial-subscriptions.md)
- [Cree suscripciones adicionales](../../ready/azure-best-practices/scale-subscriptions.md) para escalar el entorno de Azure.
- [Organice y administre sus suscripciones](../../ready/azure-best-practices/organize-subscriptions.md) mediante grupos de administración de Azure.

## <a name="modeling-your-organization"></a>Modelado de la organización

Como cada organización es diferente, los grupos de administración de Azure están diseñados para ser flexibles. El modelado de su entorno en la nube para reflejar la jerarquía de la organización le ayuda a definir y aplicar directivas en los niveles más altos de la jerarquía, y a confiar en la herencia para asegurarse de que esas directivas se aplicarán automáticamente a los grupos de administración situados más abajo. Aunque las suscripciones se pueden trasladar entre diferentes grupos de administración, resulta útil diseñar una jerarquía inicial de grupos de administración que refleje sus necesidades organizativas de forma anticipada.

Antes de finalizar el diseño de la suscripción, considere cómo las decisiones sobre la [coherencia de recursos](../resource-consistency/index.md) pueden influir en las opciones de diseño.

> [!NOTE]
> Los Contratos Enterprise (EA) de Azure le permiten definir otra jerarquía organizativa con fines de facturación. Esta jerarquía es distinta de la jerarquía del grupo de administración, que se centra en proporcionar un modelo de herencia para aplicar fácilmente directivas adecuadas y control de acceso a los recursos.

## <a name="subscription-design-strategies"></a>Estrategias de diseño de suscripciones

Tenga en cuenta las siguientes estrategias de diseño de suscripciones para dar respuesta a sus prioridades empresariales.

### <a name="workload-separation-strategy"></a>Estrategia de separación de cargas de trabajo

A medida que una organización agrega nuevas cargas de trabajo a la nube, las diferentes propiedades de las suscripciones o una separación básica de las responsabilidades puede resultar en varias suscripciones en los grupos de administración de producción y de no producción. Aunque este enfoque proporciona una separación básica de cargas de trabajo, no aprovecha de manera significativa el modelo de herencia a la hora de aplicar automáticamente directivas en un subconjunto de las suscripciones.

![Estrategia de separación de cargas de trabajo](../../_images/ready/management-group-hierarchy-v2.png)

### <a name="application-category-strategy"></a>Estrategia de categoría de aplicación

A medida que crece la superficie en la nube de la organización se crean normalmente suscripciones para admitir aplicaciones que tienen diferencias fundamentales con respecto a importancia para la empresa, requisitos de cumplimiento, controles de acceso o necesidades de protección de datos. En las suscripciones de producción y de no producción, las suscripciones que admiten estas categorías de aplicaciones se organizan en el grupo de administración de producción o de no producción según corresponda. Normalmente, el personal central de operaciones de TI posee y administra estas suscripciones.

![Estrategia de categoría de aplicación](../../_images/infra-subscriptions/application.png)

Cada organización categorizará las aplicaciones de forma diferente, a menudo separarán las suscripciones basadas en aplicaciones o servicios específicos o en arquetipos de aplicación. Esta categorización a menudo está diseñada para admitir cargas de trabajo que es probable que consuman la mayor parte de los límites de recursos de una suscripción o cargas de trabajo críticas independientes para asegurarse de que no compiten con otras cargas de trabajo dentro de estos límites. Entre las cargas de trabajo que pueden justificar una suscripción independiente se incluyen:

- Cargas de trabajo críticas.
- Aplicaciones que forman parte del "coste de bienes vendidos" (COGS) dentro de la empresa. Ejemplo: cada instancia del widget de la empresa X contiene un módulo de IoT de Azure que envía datos de telemetría. Esto puede requerir una suscripción dedicada para fines de contabilidad o gobernanza como parte del COGS.
- Aplicaciones sujetas a requisitos legales (como HIPAA o FedRAMP).

### <a name="functional-strategy"></a>Estrategia funcional

La estrategia funcional organiza las suscripciones y cuentas a lo largo de líneas funcionales como finanzas, ventas o soporte técnico de TI, mediante una jerarquía de grupos de administración.

### <a name="business-unit-strategy"></a>Estrategia de la unidad de negocio

Esta estrategia agrupa las suscripciones y cuentas en función de categorías de pérdidas y ganancias, unidades de negocio, divisiones, centros de beneficios o estructuras empresariales similares mediante una jerarquía de grupo de administración.

### <a name="geographic-strategy"></a>Estrategia geográfica

Para organizaciones con operaciones globales, la estrategia geográfica agrupa las suscripciones y cuentas en función de las regiones geográficas mediante una jerarquía de administración de grupos.

## <a name="mixing-subscription-strategies"></a>Estrategias de suscripciones mixtas

Las jerarquías de los grupos de administración pueden incluir hasta seis niveles de profundidad. Esto le proporciona flexibilidad para crear una jerarquía que combina varias de estas estrategias para satisfacer sus necesidades organizativas. Por ejemplo, el diagrama siguiente muestra una jerarquía organizativa que combina una estrategia de unidad de negocio con una estrategia geográfica.

![Estrategia de suscripción mixta](../../_images/infra-subscriptions/mixed.png)

## <a name="related-resources"></a>Recursos relacionados

- [Administración del acceso a recursos de Azure](../../govern/resource-consistency/resource-access-management.md)
- [Varias capas de gobernanza en grandes empresas](../../govern/guides/complex/multiple-layers-of-governance.md)
- [Varias regiones geográficas](../../migrate/azure-best-practices/multiple-regions.md)

## <a name="next-steps"></a>Pasos siguientes

El diseño de suscripciones es solo uno de los principales componentes de infraestructura que requieren decisiones de arquitectura durante un proceso de adopción de la nube. Visite la [introducción a las guías de decisión](../index.md) para más información sobre las estrategias adicionales que se usan al tomar decisiones de diseño para otros tipos de infraestructura.

> [!div class="nextstepaction"]
> [Guías de decisiones sobre arquitectura](../index.md)
