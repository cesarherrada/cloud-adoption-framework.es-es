---
title: Impacto de las decisiones de mercados globales
description: Use Cloud Adoption Framework para Azure con el fin de comprender cómo las decisiones de los mercados globales pueden afectar al recorrido de transformación a la nube.
author: BrianBlanchard
ms.author: brblanch
ms.date: 04/04/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: strategy
ms.openlocfilehash: e2e0399f227f69ef1ae27b6b23a847a6508650d4
ms.sourcegitcommit: ea63be7fa94a75335223bd84d065ad3ea1d54fdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80353483"
---
<!-- markdownlint-disable MD026 -->

# <a name="how-will-global-market-decisions-affect-the-transformation-journey"></a>¿Cómo afectarán las decisiones de mercados globales al recorrido de transformación?

La nube abre nuevas oportunidades para operar a escala global. Las barreras para las operaciones globales se reducen significativamente al permitir a las empresas implementar activos en el mercado sin necesidad de realizar fuertes inversiones en nuevos centros de datos. Desafortunadamente, esto también agrega una gran complejidad desde una perspectiva técnica y legal.

## <a name="data-sovereignty"></a>Soberanía de los datos

Muchas regiones geopolíticas han establecido leyes de soberanía de datos. Estas regulaciones restringen dónde se pueden almacenar los datos, qué datos pueden abandonar el país de origen y qué datos se pueden recopilar sobre los ciudadanos de esa región. Antes de trabajar con cualquier solución basada en la nube en una zona geográfica extranjera, debe saber cómo administra la soberanía de los datos el proveedor de nube. [Aquí](https://azure.microsoft.com/global-infrastructure/geographies) encontrará más información sobre el enfoque de Azure para cada zona geográfica. Para más información sobre el cumplimiento en Azure, consulte [Privacidad en Microsoft](https://www.microsoft.com/trustcenter/privacy) en el centro de confianza de Microsoft.

En el resto de este artículo, se da por supuesto que el asesor legal ha revisado y aprobado las operaciones en un país extranjero.

## <a name="business-units"></a>Unidades de negocio

Es importante conocer qué unidades de negocio operan en países extranjeros y qué países se ven afectados. Esta información se usará para diseñar soluciones para el hospedaje, la facturación y las implementaciones en el proveedor de la nube.

## <a name="employee-usage-patterns"></a>Patrones de uso de empleados

Es importante conocer cómo los usuarios globales acceden a las aplicaciones que no están hospedadas en el mismo país que el usuario. Las redes de área extensa (WAN) globales enrutan a los usuarios según los contratos de red existentes. En los entornos locales tradicionales, algunas restricciones limitan el diseño de WAN. Estas restricciones pueden dar lugar a experiencias de usuario deficientes si no se comprenden correctamente antes de la adopción de la nube.

En un modelo en la nube, el Internet de los productos también abre muchas opciones nuevas. La comunicación de la distribución de los empleados en varias zonas geográficas puede ayudar al equipo de adopción de la nube a diseñar soluciones WAN que crean experiencias de usuario positivas **y** a reducir potencialmente los costos de red.

## <a name="external-user-usage-patterns"></a>Patrones de uso de usuarios externos

Es igualmente importante comprender los patrones de uso de los usuarios externos, como los clientes o asociados. De forma muy similar a los patrones de uso de los empleados, los patrones de uso de usuarios externos pueden afectar negativamente al rendimiento de las implementaciones en la nube. Si una base de usuarios grande o crítica reside en un país extranjero, podría ser aconsejable incluir una estrategia de implementación global en el diseño de la solución global.

## <a name="next-steps"></a>Pasos siguientes

Obtenga información sobre las [aptitudes necesarias durante la fase de estrategia](./suggested-skills.md) del recorrido de adopción de la nube.

> [!div class="nextstepaction"]
> [Aptitudes pertinentes para la estrategia](./suggested-skills.md)
