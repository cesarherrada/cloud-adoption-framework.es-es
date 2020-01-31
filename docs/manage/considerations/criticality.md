---
title: 'Importancia crítica para la empresa: administración y operaciones en la nube'
description: 'Importancia crítica para la empresa: administración y operaciones en la nube'
author: BrianBlanchard
ms.author: brblanch
ms.date: 10/17/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.openlocfilehash: 3232d0544f0382c6277e3a2898a95aa0c2f11ddd
ms.sourcegitcommit: 2362fb3154a91aa421224ffdb2cc632d982b129b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76807842"
---
# <a name="business-criticality-in-cloud-management"></a>Importancia crítica para la empresa en la administración de la nube

En cada empresa, existe un pequeño número de cargas de trabajo que son demasiado importantes como para que produzcan errores. Estas cargas de trabajo se consideran críticas. Cuando esas cargas de trabajo experimentan interrupciones o una degradación del rendimiento, el impacto negativo en los ingresos y la rentabilidad se puede notar en toda la empresa.

En el otro extremo del espectro, pueden pasar meses sin que se utilicen algunas cargas de trabajo. En este caso, tampoco se quiere que experimenten un bajo rendimiento o interrupciones, aunque el efecto será aislado y limitado.

Comprender la importancia crítica de cada carga de trabajo de la cartera de TI es el primer paso para establecer compromisos mutuos con la administración de la nube.
El diagrama siguiente ilustra una alineación común entre la escala de importancia crítica que se debe seguir y los compromisos estándar realizados por la empresa.

![Alineación del nivel de administración e importancia crítica](../../_images/manage/cloud-criticality-alignment.png)

## <a name="criticality-scale"></a>Escala de importancia crítica

El primer paso en cualquier trabajo de alineación de la importancia crítica para la empresa es crear una escala. En la tabla siguiente se presenta una escala de ejemplo que se usará como referencia, o plantilla, para crear su propia escala.

| Grado de importancia | Visión empresarial |
| --------- | --------- |
| Críticas |  Afecta a la misión de la empresa y puede afectar notablemente a los balances corporativos de pérdidas y ganancias. |
| Crítico para la unidad | Afecta a la misión de una unidad de negocio específica y a sus balances de pérdidas y ganancias. |
| Alto | Aunque puede que no entorpezca la misión, afecta a los procesos de importancia alta. En el caso de las interrupciones, las pérdidas mensurables se pueden cuantificar. |
| Media | Es problema que se produzca un impacto en los procesos. Las pérdidas son bajas o imperceptibles, pero pueden producirse daños en la marca o pérdidas en la etapa inicial de la producción. |
| Bajo | El impacto en los procesos empresariales es imperceptible. No es probable que se produzcan daños en la marca ni pérdidas en la etapa inicial de producción. Lo más probable es que se produzca un impacto localizado en un solo equipo. |
| No compatible | Ningún propietario, equipo o proceso de negocio asociado a esta carga de trabajo puede justificar una inversión en la administración continua de la carga de trabajo. |

Es habitual que las empresas incluyan clasificaciones adicionales de importancia crítica específicas de su sector, segmento vertical o proceso empresarial determinado. Entre los ejemplos de clasificaciones adicionales se incluyen:

- **Crítica para el cumplimiento:** en sectores muy regulados, algunas cargas de trabajo pueden ser críticas como parte de las labores de cumplimiento de la normativa.
- **Crítica para la seguridad:** es posible que algunas cargas de trabajo no sean críticas, pero las interrupciones podrían provocar la pérdida de datos o el acceso no deseado a información protegida.
- **Crítica para la protección:** cuando la vida o la seguridad física de empleados y clientes están en juego durante una interrupción, puede ser aconsejable clasificar las cargas de trabajo como críticas para la seguridad.

## <a name="importance-of-accurate-criticality"></a>Valor de la importancia crítica precisa

Más adelante en el proceso de adopción de la nube, el equipo de administración de la nube usará esta clasificación para determinar la cantidad de trabajo necesaria para cumplir los niveles de importancia crítica alineados. En entornos locales, la administración de operaciones se suele procurar de forma central y se trata como una carga empresarial necesaria, con poco o ningún costo operativo adicional. En la nube, la administración de operaciones (como la de toda la nube) se procura por recurso según los costos operativos mensuales.

Dado que hay un costo claro y directo para la administración de operaciones en la nube, es importante alinear correctamente los costos y las escalas de importancia crítica deseadas.

## <a name="select-a-default-criticality"></a>Selección de una importancia crítica predeterminada

La revisión inicial de cada carga de trabajo de la cartera puede llevar mucho tiempo. Para tener la seguridad de que este trabajo no bloquea la estrategia en la nube más amplia, se recomienda que los equipos lleguen a un acuerdo sobre la importancia crítica predeterminada que se aplicará a todas las cargas de trabajo.

En función de la tabla de escala de importancia crítica anterior, se recomienda adoptar el nivel de importancia crítica *Medio* como valor predeterminado. De esta forma, el equipo de estrategia en la nube podrá identificar rápidamente las cargas de trabajo que requieren un nivel más alto de importancia crítica.

## <a name="use-the-template"></a>Uso de la plantilla

Los siguientes pasos se aplican utiliza el [libro de administración de las operaciones](https://raw.githubusercontent.com/microsoft/CloudAdoptionFramework/master/manage/opsmanagementworkbook.xlsx) para planear la administración de la nube.

1. Registre la escala de importancia crítica en la pestaña de **escala** del libro.
2. Actualice cada una de las cargas de trabajo del *ejemplo* o de la *plantilla limpia* para reflejar el nivel de importancia predeterminado en la columna *Importancia crítica*.
3. La empresa debe introducir los valores correctos para reflejar cualquier desviación de la importancia crítica predeterminada.

## <a name="next-steps"></a>Pasos siguientes

Cuando el equipo haya definido la importancia crítica para la empresa, puede [calcular y registrar el impacto empresarial](./impact.md).

> [!div class="nextstepaction"]
> [Cálculo y registro del efecto para la empresa](./impact.md)
