---
title: Riesgos empresariales de Cost Management
description: Comprenda y consulte ejemplos de un proceso de adopción normal por parte de un cliente de una materia de administración de costos en una estrategia de gobernanza de la nube. 
author: BrianBlanchard
ms.author: brblanch
ms.date: 09/17/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: govern
ms.custom: governance
ms.openlocfilehash: 38fb0523b2c5915a351223fdb603dbb0cacbf602
ms.sourcegitcommit: ea63be7fa94a75335223bd84d065ad3ea1d54fdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80357142"
---
<!-- cSpell:ignore prepurchases -->

# <a name="cost-management-motivations-and-business-risks"></a>Motivaciones de la administración de costos y riesgos empresariales

En este artículo se describen las razones por las que los clientes normalmente adoptan una materia de administración de costos dentro de una estrategia de gobernanza en la nube. También se proporcionan algunos ejemplos de riesgos empresariales que impulsan las declaraciones de directiva.

<!-- markdownlint-disable MD026 -->

## <a name="is-cost-management-relevant"></a>¿Es pertinente la administración de costos?

En términos de gobernanza de costos, la adopción de la nube genera un cambio de paradigma. La administración de costos en un mundo local tradicional se basa en ciclos de actualización, adquisiciones de centros de datos, renovaciones de hosts y problemas de mantenimiento recurrentes. Puede prever, planear y ajustar cada uno de estos costos para alinearlos con los presupuestos anuales de gastos de capital.

Para las soluciones de nube, muchas empresas suelen adoptar un enfoque más reactivo ante la administración de costos. En muchos casos, las empresas compran previamente, o se comprometen a usar, una cantidad determinada de servicios en la nube. Este modelo da por supuesto que maximizar los descuentos, en función de cuánto planee gastar la empresa con un proveedor de servicios en la nube específico, crea la percepción de un ciclo de costos planeado y proactivo. Sin embargo, esa percepción solo se convertirá en una realidad si la empresa también implementa materias maduras de administración de costos.

La nube ofrece capacidades de autoservicio que antes no se conocían en los centros de datos locales tradicionales. Estas nuevas capacidades permiten a las empresas ser más ágiles, menos restrictivas y más abiertas en relación con la adopción de nuevas tecnologías. Sin embargo, la desventaja del autoservicio es que los usuarios finales pueden superar los presupuestos asignados sin saberlo. A la inversa, los mismos usuarios pueden experimentar un cambio en los planes y, de forma inesperada, no utilizar la cantidad de servicios en la nube previstos. El potencial de cambio en cualquier dirección justifica la inversión en una materia de administración de costos dentro del equipo de gobernanza.

## <a name="business-risk"></a>Riesgo empresarial

La materia de Cost Management intenta abordar los principales riesgos empresariales relacionados con los gastos que se derivan de hospedar cargas de trabajo basadas en la nube. Trabaje con su empresa para identificar estos riesgos y supervise cada uno de ellos para determinar su pertinencia a medida que planee y aplique sus implementaciones en la nube.

Los riesgos variarán según la organización, pero los siguientes sirven como riesgos comunes relacionados con los costos que puede usar como punto de partida para debatir en el seno de su equipo de gobernanza de la nube:

- **Control del presupuesto:** No controlar el presupuesto puede llevar a un gasto excesivo con un proveedor de servicios en la nube.
- **Pérdida de uso.** Las compras previas o los compromisos previos que no se utilicen pueden generar inversiones perdidas.
- **Anomalías en el gasto.** Los aumentos inesperados en cualquier dirección pueden ser indicadores de un uso inadecuado.
- **Recursos sobreaprovisionados.** La implementación de los recursos en una configuración que supere las necesidades de una aplicación o máquina virtual (VM) puede dar lugar a un desperdicio de los recursos.

## <a name="next-steps"></a>Pasos siguientes

Utilice la [plantilla de administración de la nube](./template.md) para documentar los riesgos empresariales que probablemente se presentarán en el plan de adopción de la nube actual.

Una vez que se consigue una comprensión realista de los riesgos empresariales, el siguiente paso es documentar la tolerancia al riesgo de la empresa y los indicadores y métricas clave para supervisar esa tolerancia.

> [!div class="nextstepaction"]
> [Descripción de indicadores, métricas y tolerancia al riesgo](./metrics-tolerance.md)
