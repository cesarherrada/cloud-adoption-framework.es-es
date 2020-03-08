---
title: Guía de gobernanza para empresas complejas
description: Siga a una empresa ficticia compleja a través de las distintas fases de la madurez de la gobernanza, cuando define un producto mínimo viable (MVP) en función de procedimientos recomendados.
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: govern
ms.custom: governance
ms.openlocfilehash: 04f8c5e53eea03c0a25c84c03a09c4fa0ec60bff
ms.sourcegitcommit: 58ea417a7df3318e3d1a76d3807cc4e7e3976f52
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2020
ms.locfileid: "78892105"
---
# <a name="governance-guide-for-complex-enterprises"></a>Guía de gobernanza para empresas complejas

## <a name="overview-of-best-practices"></a>Introducción sobre los procedimientos recomendados

Esta guía de gobernanza muestra las experiencias de una empresa ficticia a través de diversas fases de madurez del proceso de gobernanza. Se basa en experiencias reales de los clientes. Los procedimientos recomendados sugeridos se basan en las restricciones y necesidades de la empresa ficticia.

Como punto de inicio rápido, esta información general define un producto viable mínimo (MVP) para la gobernanza en función de los procedimientos recomendados. También proporciona vínculos a algunas mejoras de gobernanza que agregan más procedimientos recomendados a medida que emergen nuevos riesgos técnicos o empresariales.

> [!WARNING]
> Este MVP es un punto de inicio de la base de referencia, basado en un conjunto de suposiciones. Incluso este conjunto mínimo de procedimientos recomendados se basa en directivas corporativas controladas por tolerancias al riesgo y riesgos empresariales únicos. Para ver si estas suposiciones se aplican a usted, lea la [narrativa más larga](./narrative.md) que sigue este artículo.

### <a name="governance-best-practices"></a>Procedimientos recomendados sobre gobernanza

Este procedimiento recomendado actúa como la base para que una organización agregue barreras de seguridad de forma rápida y coherente en varias suscripciones de Azure.

### <a name="resource-organization"></a>Organización de recursos

En el siguiente diagrama se muestra la jerarquía de MVP de gobernanza para organizar recursos.

![Diagrama de organización de los recursos](../../../_images/govern/resource-organization.png)

Todas las aplicaciones deben implementarse en el área adecuada de la jerarquía de grupos de recursos, suscripción y grupos de administración. Durante el planeamiento de la implementación, el equipo de gobernanza en la nube creará los nodos necesarios en la jerarquía para capacitar a los equipos de adopción de la nube.

1. Defina un grupo de administración para cada unidad de negocio con una jerarquía detallada que refleje primero la zona geográfica y, después, el tipo de entorno (por ejemplo, los entornos de producción o de no producción).

1. Cree una suscripción de producción y otra de no producción para cada combinación única de unidad de negocio o zona geográfica discretas. La creación de varias suscripciones requiere extremar la atención. Para más información, consulte la [Guía de decisiones de suscripción](../../../decision-guides/subscriptions/index.md).

1. Aplique una [nomenclatura coherente](../../../ready/azure-best-practices/naming-and-tagging.md) en cada nivel de esta jerarquía de agrupación.

1. Los grupos de recursos se deben implementar de forma que tengan en cuenta el ciclo de vida de su contenido. Los recursos que se desarrollan, se administran y se retiran juntos pertenecen al mismo grupo. Para más información sobre los procedimientos recomendados para usar grupos de recursos, [consulte esto](../../../decision-guides/resource-consistency/index.md).

1. La [selección de región](../../../migrate/azure-best-practices/multiple-regions.md) es sumamente importante y se debe tener muy en cuenta para que las redes, la supervisión y la auditoría estén en vigor para la conmutación por error o la conmutación por recuperación así como para la confirmación de que las [SKU necesarias están disponibles en las regiones preferidas](https://azure.microsoft.com/global-infrastructure/services).

![Diagrama de organización de recursos de grandes empresas](../../../_images/govern/large-enterprise-resource-organization.png)

Estos patrones permiten crecer sin que la jerarquía sea innecesariamente complicada.

[!INCLUDE [governance-of-resources](../../../../includes/caf-governance-of-resources.md)]

<!-- See comments for suggestion to possibly add here -->

## <a name="incremental-governance-improvements"></a>Mejoras de gobernanza incremental

Una vez que se ha implementado este MVP, se pueden incorporar capas de gobernanza rápidamente en el entorno. Estas son algunas formas de mejorar el MVP para satisfacer necesidades empresariales específicas:

- [Base de referencia de seguridad para datos protegidos](./security-baseline-improvement.md)
- [Configuraciones de recursos para aplicaciones críticas](./resource-consistency-improvement.md)
- [Controles de administración de costos](./cost-management-improvement.md)
- [Controles para la mejora incremental de la nube múltiple](./multicloud-improvement.md)

<!-- markdownlint-disable MD026 -->

## <a name="what-does-this-guidance-provide"></a>¿Qué proporciona esta guía?

En el MVP, prácticas y herramientas de la materia de [aceleración de la implementación](../../deployment-acceleration/index.md) se establecen para aplicar rápidamente la directiva corporativa. En concreto, el MVP usa Azure Blueprints, Azure Policy y grupos de administración de Azure para aplicar algunas directivas corporativas básicas, tal como se define en la narrativa de esta empresa ficticia. Dichas directivas corporativas se aplican mediante plantillas de Azure Resource Manager y directivas de Azure para establecer una base de referencia pequeña para la identidad y la seguridad.

![Ejemplo de un MVP de gobernanza incremental](../../../_images/govern/governance-mvp.png)

## <a name="incremental-improvements-to-governance-practices"></a>Mejora incremental de los procedimientos de gobernanza

Con el tiempo, este MVP de gobernanza se usará para mejorar de forma incremental las prácticas de gobernanza. A medida que avanza la adopción, aumenta el riesgo empresarial. Para administrar esos riesgos, se adaptarán varias materias dentro del modelo de gobernanza de Cloud Adoption Framework. En artículos posteriores de esta serie se explica la evolución de la directiva corporativa que afecta a la empresa ficticia. Estos cambios se producen en cuatro materias:

- Base de referencia de identidad, a medida que las dependencias de migración cambian en la narración.
- Administración de costos, a medida que la adopción se escala.
- Base de referencia de seguridad, a medida que los datos protegidos se implementan.
- Coherencia de recursos, a medida que las operaciones de TI empiezan a admitir cargas de trabajo críticas.

![Ejemplo de un MVP de gobernanza incremental](../../../_images/govern/governance-improvement-large.png)

## <a name="next-steps"></a>Pasos siguientes

Ahora que se ha familiarizado con el producto viable mínimo de gobernanza y con los próximos cambios de la gobernanza, lea la documentación complementaria para obtener más contexto.

> [!div class="nextstepaction"]
> [Lectura de la narrativa de apoyo](./narrative.md)
