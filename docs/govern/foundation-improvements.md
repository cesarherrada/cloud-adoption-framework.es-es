---
title: Mejora de una base de gobernanza de la nube inicial
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: Aprenda a mejorar gradualmente la base de gobernanza de la nube inicial.
author: BrianBlanchard
ms.author: brblanch
ms.date: 09/13/2019
ms.topic: landing-page
ms.service: cloud-adoption-framework
ms.subservice: govern
ms.custom: governance
layout: LandingPage
ms.openlocfilehash: 315797d7ef4ab93d5d386ee32a499f4172752687
ms.sourcegitcommit: 50788e12bb744dd44da14184b3e884f9bddab828
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2019
ms.locfileid: "74159932"
---
# <a name="improve-your-initial-cloud-governance-foundation"></a>Mejora de una base de gobernanza de la nube inicial

En este artículo se supone que ha establecido una [base de gobernanza de la nube inicial](./initial-foundation.md). A medida que se implementa el plan de adopción de la nube, surgen riesgos tangibles a partir de los enfoques propuestos mediante los cuales los equipos quieren adoptar la nube. A medida que estos riesgos afloren en las conversaciones de planeamiento del lanzamiento, use la siguiente cuadrícula para identificar con rapidez algunos procedimientos recomendados para aprovechar el plan de adopción y evitar que los riesgos se conviertan en amenazas reales.

## <a name="maturity-vectors"></a>Vectores de madurez

En cualquier momento, se pueden aplicar los procedimientos recomendados siguientes a los fundamentos iniciales para la gobernanza a fin de afrontar los riesgos o necesidades que se mencionan en la siguiente tabla.

> [!IMPORTANT]
> La organización de los recursos puede afectar al modo en que estos procedimientos recomendados se aplican. Es importante comenzar con las recomendaciones que mejor se adapten a la base de gobernanza de la nube inicial que implementó en el paso anterior.

|Riesgo o necesidad | Empresa estándar | Empresa compleja |
|---|---|---|
|Información confidencial en la nube|[Mejora de la materia](./guides/standard/security-baseline-improvement.md)|[Mejora de la materia](./guides/complex/security-baseline-improvement.md)|
|Aplicaciones críticas en la nube|[Mejora de la materia](./guides/standard/resource-consistency-improvement.md)|[Mejora de la materia](./guides/complex/resource-consistency-improvement.md)|
|Administración de costos de la nube|[Mejora de la materia](./guides/standard/cost-management-improvement.md)|[Mejora de la materia](./guides/complex/cost-management-improvement.md)|
|Nube múltiple|[Mejora de la materia](./guides/standard/multicloud-improvement.md)|[Mejora de la materia](./guides/complex/multicloud-improvement.md)|
|Administración de identidades compleja o heredada|N/D|[Mejora de la materia](./guides/complex/identity-baseline-improvement.md)|
|Varias capas de gobernanza|N/D|[Mejora de la materia](./guides/complex/multiple-layers-of-governance.md)|

## <a name="next-steps"></a>Pasos siguientes

Además de la aplicación de los procedimientos recomendados, la metodología de gobernanza de Cloud Adoption Framework se puede personalizar para adaptarse a restricciones empresariales específicas. Después de seguir las recomendaciones aplicables, [evalúe las directivas corporativas para comprender los requisitos de personalización adicionales](./corporate-policy.md).

> [!div class="nextstepaction"]
> [Evaluación de las directivas corporativas](./corporate-policy.md)
