---
title: 'Gobernanza para empresas estándar: Directiva corporativa inicial'
description: Use Cloud Adoption Framework de Azure para definir la posición inicial de gobernanza, riesgos en las primeras etapas, instrucciones iniciales para las directivas y procesos de aplicación tempranos.
author: BrianBlanchard
ms.author: brblanch
ms.date: 09/05/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: govern
ms.custom: governance
ms.openlocfilehash: 64f04fe32445f79f36fe3846f16e3296e9424130
ms.sourcegitcommit: 10637acba8c857a6f5aa8c4a80c0649903f60402
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78170943"
---
# <a name="standard-enterprise-governance-guide-initial-corporate-policy-behind-the-governance-strategy"></a>Guía de gobernanza para empresas estándar: directiva corporativa inicial que está detrás de la estrategia de gobernanza

La siguiente directiva corporativa define una posición de gobernanza inicial, que es el punto de inicio de esta guía. En este artículo se definen riesgos incipientes, las declaraciones de directiva iniciales y los procesos iniciales para aplicar las declaraciones de directiva.

> [!NOTE]
>La directiva corporativa no es un documento técnico, pero promueve muchas decisiones técnicas. El producto mínimo viable de gobernanza descrito en la [información general](./index.md) deriva, en última instancia, de esta directiva. Antes de implementar un producto mínimo viable de gobernanza, su organización debe desarrollar una directiva corporativa en función de sus propios objetivos y riesgos empresariales.

## <a name="cloud-governance-team"></a>Equipo de gobernanza de la nube

En esta narración, el equipo de gobernanza de la nube consta de dos administradores de sistemas que han reconocido la necesidad de gobernanza. Durante los próximos meses, tendrán que hacerse cargo de limpiar la gobernanza de la presencia en la nube de la empresa, lo cual les hará merecedores del sobrenombre de _custodios de la nube_. En iteraciones posteriores, es probable que este sobrenombre cambie.

[!INCLUDE [business-risk](../../../../includes/business-risks.md)]

## <a name="tolerance-indicators"></a>Indicadores de tolerancia

La tolerancia al riesgo actual es alta y el apetito por invertir en la gobernanza de la nube es bajo. Como tales, los indicadores de tolerancia actúan como sistema de advertencia anticipado para desencadenar una mayor inversión de tiempo y energía. Si se observan los indicadores siguientes, debe mejorar de forma iterativa la estrategia de gobernanza.

- **Administración de costos:** La escala de la implementación supera los límites predeterminados de número de recursos o el costo mensual.
- **Base de referencia de la seguridad:** inclusión de datos protegidos en planes de adopción de la nube definidos.
- **Coherencia de los recursos:** inclusión de cualquier aplicación crítica en planes de adopción de la nube definidos.

[!INCLUDE [policy-statements](../../../../includes/policy-statements.md)]

## <a name="next-steps"></a>Pasos siguientes

Esta directiva corporativa prepara el equipo de gobernanza de la nube para implementar el producto viable mínimo de gobernanza, que será la base para la adopción. El siguiente paso es implementar dicho producto mínimo viable.

> [!div class="nextstepaction"]
> [Explicación de los procedimientos recomendados](./prescriptive-guidance.md)
